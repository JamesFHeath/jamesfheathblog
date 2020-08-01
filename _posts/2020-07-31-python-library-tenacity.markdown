---
layout: post
title:  "Python Library: Tenacity"
categories: python programming
tags: python tenacity
---

### Introduction
Today I want to write about one of my favorite Python libraries, [tenacity](https://pypi.org/project/tenacity/). 
Tenacity is a library for retrying code after a failure. 
This failure could be a raised exception, a network timeout, a 500 HTTP response, anything. 
Tenacity is simple, and uses function decorators to implement standard or custom tenacity logic. 

### Retrying After Exceptions
To get tenacity working, **pip install tenacity** and then **from tenacity import \***. 
Tenacity uses function decorators to tell a function to retry.
By default, @retry will work after any exception. 

{% highlight python %}
from tenacity import *

@retry
def exception_function():
    raise Exception('failure')
# @retry will retry the function indefinitely
{% endhighlight %}

Several time and execution count based parameters can be added to the decorator. 

{% highlight python %}
from tenacity import * 

@retry(stop=stop_after_attempt(5))
def max_attempts():
    print('Runs 5 Times')
    raise Exception

@retry(wait=wait_fixed(2))
def fixed_wait_attempts():
    print('Waits 2 Seconds Between Retries')
    raise Exception

@retry(stop=stop_after_attempt(5), wait=wait_fixed(2))
def max_and_fixed_wait_attempts():
    print('Runs 5 Times AND Waits 2 Seconds Between Retries')
    raise Exception

# Expontential backoff is important for network calls. 
@retry(wait=wait_exponential(multiplier=1, max=10))
def exponential_backoff_attempts():
    print('Runs at second intervals of 0, 2, 4, 8, 10, 10, 10...')
    raise Exception
{% endhighlight %}

### Custom Retrying Logic
Retrying a function based on the type of exception raised can be very useful. 
In this example, the function only retries on IOError and ConnectionError exceptions, but allows TypeError to be raised immediately. 
This would be useful for retrying failed input/output calls and network calls. 

{% highlight python %}
@retry(stop=stop_after_attempt(3), retry=retry_if_exception_type((IOError, ValueError)))
def different_exceptions_possible(x):
    if x == 1:
        print('IO Error because x is 1')
        raise IOError
    elif x == 2:
        print('Connection Error because x is 2')
        raise ConnectionError
    elif x == 3:
        print('Type Error because x is 3')
        raise TypeError
    else:
        return 'success'

print(different_exceptions_possible(1))
# 'IO Error because x is 1' printed 3 times before exception raised
print(different_exceptions_possible(2))
# 'Connection Error because x is 2' printed 3 times before exception raised
print(different_exceptions_possible(3))
# Type Error is raised immediately because the retry ignores it
{% endhighlight %}

Sometimes a function should be retried even if it completes without an exception. 
Tenacity allows custom retrying functions to be used.
If the custom function returns True, the original function is retried. 
For example, this code retries if the HTTP response is not in the success range of 200 to 299. 

{% highlight python %}
@retry(retry=retry_if_result(is_invalid_code))
def my_success_http_request():
    print('success')
    return 200

print(my_success_http_request())
# success 
# 200

@retry(retry=retry_if_result(is_invalid_code))
def my_failure_http_request():
    print('failure')
    return 400

print(my_failure_http_request())
# failure
# failure
# failure
# ....
{% endhighlight %}