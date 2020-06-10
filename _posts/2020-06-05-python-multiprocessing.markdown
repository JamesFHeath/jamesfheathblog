---
layout: post
title:  "Python Multiprocessing Primer"
date:   2020-06-05 18:36:08 -0400
categories: python programming
tags: python multiprocessing 
---

### Introduction

Multiprocessing in Python is useful for CPU intensive processes that can be done in parallel. 
I've found a lot of uses in tranforming several GB of data. Multiprocessing falls into the sweet spot between a quick script and using a big data system like [Spark](https://spark.apache.org/).

### Multiprocessing vs. Multithreading

Unsurprisingly, multithreading creates new threads and multiprocessing creates new processes. 
New threads spin up quickly, and are non blocking on I/O operations like network calls and disk read/write.
New processes have more overhead when starting up, but are able to utilize multiple CPU cores and process data in parallel.  

### Quickstart Code

It's simple to get up and running with multiprocessing by creating a pool of processes that can execute functions. 
For data processing I will make the number of processes equal to the number of cores my CPU has -1. 
The basic setup is to create a list of parameters that need to be operated on, then pass the function and the paramters to [pool.starmap()](https://docs.python.org/3.7/library/multiprocessing.html#multiprocessing.pool.Pool.starmap).
The results will come back as an iterable that you can then operate on with a simple "for" expression.

{% highlight python %}
import multiprocessing

data_to_process = [a, b, c, d, e, f, g]
other_args = 123

num_processes = 7 
with multiprocessing.Pool(num_processes) as pool:
        params = []
        for data in data_to_process:
            params.append((data, other_args)) # Tuple of args here
        for result1, result2 in pool.starmap(my_function, params):
            operate_on_results(result1, result2)

{% endhighlight %}

### Pitfalls

* Forked processes cannot have child processes or child threads. 
* I have not found a way to debug programs with multiprocessed code. 
This is using VSCode and Windows, so it may be a system issue. 
* Logging is a challenge, I'm writing a future blog post to go over my logging approach.
* Exceptions that are encountered may not propagate and stop execution, I use a helper function that surrounds the processes in a try/except, ususally with a SystemExit: 
{% highlight python %}
def execute_processes(pool, f, params, logger):
    """ Wraps a starmap in a try/except. Ease of use function.

    Arguments:
        pool (multiprocessing.Pool): pool to use to execute
        f (func): function to execute
        params (list(tuple)): parameters to apply to f
        logger (logger): Logging object

    Returns:
        iterable: iterable result of the starmap
    """
    try:
        return pool.starmap(f, params)
    except Exception as e:
        logger.exception(e)
        raise SystemExit
{% endhighlight %}
* When passing parameters to a process, keep the size of any individual object passed to under 2GB or you will encounter a runtime error. 
I get around this issue by using the pickle library and saving parameters to disk. 
I'm not exactly clear on why this is a limitation, but it has something to do with the underlying C struct having a signed 32 bit int max size. 

