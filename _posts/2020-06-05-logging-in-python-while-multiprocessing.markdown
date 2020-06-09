---
layout: post
title:  "Logging in Python while Multiprocessing"
date:   2020-06-06 12:32:00 -0400
category: python
tags: python multiprocessing logging
---

### Introduction

Logging and debugging are great ways to get insights into your programs, especially while developing code.
Multiprocessing in Python introduces some quirks that make it more challenging to develop and monitor programs.
Using VSCode on Windows, I have not been able to use the debugger without crashing, so I switched to using logging for the same purpose.
Print statements can help, but logging gives a much nicer interface and ability to send outputs to different locations. 

### Naive Logging Approach 

After the debugger VSCode debugger crashed for me, I switched to logging, writing some code like this. 
(See my [previous post]({% post_url /python/2020-06-05-python-multiprocessing %}) on basic multiprocessing)
{% highlight python %}
import logging
import multiprocessing

logger = logging.getLogger()
fh = logging.FileHandler('my_log.log', encoding='utf-8')
logger.addHandler(fh)
logger.setLevel(logging.INFO)

data_to_process = [1, 2, 3]

def my_function(num, logger):
    logger.info('hello from inside process')
    return num

def run():
    num_processes = 3
    with multiprocessing.Pool(num_processes) as pool:
        logger.info('hello from before process')
        params = []
        for data in data_to_process:
            params.append((data, logger)) # Logger is passed to my_function
        for result in pool.starmap(my_function, params):
            logger.info(f'result of process: {result}')

if __name__ == '__main__':
    run()
{% endhighlight %}
It seems sensible to just pass the logger to the my_function and have it operate normally.
This seems to work!
Unfortunately, logging to a single file from multiple processes is [not supported](https://docs.python.org/3/howto/logging-cookbook.html#logging-to-a-single-file-from-multiple-processes), and you will end up with some frustrating bugs. 

### Queue Handler Approach to take Logging Events

Using the [logging cookbook](https://docs.python.org/3/howto/logging-cookbook.html#logging-to-a-single-file-from-multiple-processes) as a starting point, I've developed a few relatively simple functions to help facilitate logging with multiprocesses code. 
The solution I've settled on is to create a listener process that monitors a queue.
This queue is passed to the child processes, and they are able to log to the queue and the listener process sends the messages to the log file. 

{% highlight python %}
import logging
import logging.handlers
import multiprocessing
from os import path
import sys
import traceback

log_file_path = '' # Wherever your log files live
log_name = 'my_log'

def listener_configurer(log_name, log_file_path):
    """ Configures and returns a log file based on 
    the given name

    Arguments:
        log_name (str): String of the log name to use
        log_file_path (str): String of the log file path

    Returns:
        logger: configured logging object
    """
    logger = logging.getLogger(log_name)

    fh = logging.FileHandler(
        path.join(log_file_path, f'{log_name}.log'), encoding='utf-8')
    fmtr = logging.Formatter(
        '%(asctime)s - %(name)s - %(levelname)s - %(message)s')
    fh.setFormatter(fmtr)
    logger.setLevel(logging.INFO)
    current_fh_names = [fh.__dict__.get(
        'baseFilename', '') for fh in logger.handlers]
    if not fh.__dict__['baseFilename'] in current_fh_names: # This prevents multiple logs to the same file
        logger.addHandler(fh)

    return logger

def listener_process(queue, configurer, log_name):
    """ Listener process is a target for a multiprocess process
    that runs and listens to a queue for logging events.

    Arguments:
        queue (multiprocessing.manager.Queue): queue to monitor
        configurer (func): configures loggers
        log_name (str): name of the log to use

    Returns:
        None
    """
    configurer(log_name, log_file_path)

    while True:
        try:
            record = queue.get()
            if record is None:
                break
            logger = logging.getLogger(record.name)
            logger.handle(record)
        except Exception:
            print('Failure in listener_process', file=sys.stderr)
            traceback.print_last(limit=1, file=sys.stderr)

def my_function(num, log_queue, i):
    qh = logging.handlers.QueueHandler(log_queue)
    root_logger = logging.getLogger(path.join(log_file_path, log_name))
    root_logger.addHandler(qh)
    root_logger.setLevel(logging.INFO)

    logger = logging.getLogger(log_name).getChild(f'child_{i}') # This allows you to know what process you're in
    logger.setLevel(logging.INFO)

    logger.info('hello from inside process')

    return num

def run():
    logger = listener_configurer(log_name, log_file_path)

    manager = multiprocessing.Manager()
    log_queue = manager.Queue()
    listener = multiprocessing.Process(target=listener_process,
                                        args=(log_queue, listener_configurer, log_name))
    listener.start() # Start the listener process

    data_to_process = [1, 2, 3]

    num_processes = 3
    with multiprocessing.Pool(num_processes) as pool:
        logger.info('hello from before process')
        params = []
        for i, data in enumerate(data_to_process):
            params.append((data, log_queue, i)) # Log QUEUE is passed to my_function, along with i
        for result in pool.starmap(my_function, params):
            logger.info(f'result of process: {result}')

    log_queue.put_nowait(None) # End the queue
    listener.join() # Stop the listener

if __name__ == '__main__':
    run()
{% endhighlight %}

Output:<br>
2020-06-06 13:56:56,531 - my_log - INFO - hello from before process<br>
2020-06-06 13:56:56,825 - my_log.child_0 - INFO - hello from inside process<br>
2020-06-06 13:56:56,834 - my_log.child_1 - INFO - hello from inside process<br>
2020-06-06 13:56:56,847 - my_log.child_2 - INFO - hello from inside process<br>
2020-06-06 13:56:56,849 - my_log - INFO - result of process: 1<br>
2020-06-06 13:56:56,850 - my_log - INFO - result of process: 2<br>
2020-06-06 13:56:56,850 - my_log - INFO - result of process: 3<br>

### Summary
Creating a few simple function to help with multiprocessing logging can make life a lot easier.
I keep these function in a library so they can be called when needed. 
This process works on Windows/Linux 