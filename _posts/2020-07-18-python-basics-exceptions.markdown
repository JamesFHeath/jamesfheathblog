---
layout: post
title:  "Python Basics: Exceptions"
categories: python programming
tags: python exceptions
---


### Python Exceptions
When something goes wrong in a Python program, you will run into an exception. 
Exceptions are raised when your program attempts to perform an action that is not allowed. 
Examples would be diving by 0 or adding a str and an int.


### Handling Exceptions
Handling exceptions requires using the **try/except** keywords. 
You surround some code that could fail and cause an exception to be **raised** with the keyword try.
The except keyword surrounds what to do in the case of an exception. 

{% highlight python%}
try: 
    1 / 0 
except:
    print('Exception')    

# You can also access the specific exception raised in order to operate on it. 

try:
    'hello' + 1
except TypeError as e:
    print(f'TypeError: {e}')
# This type of output is good for logging.

{% endhighlight %}


### Raising Exceptions
Sometimes you want to inform the caller of your code that something went wrong. 

{% highlight python%}
# We define our function to operate on two variables that can be added together
def my_add_function(x, y):
    if type(x) != type(y):
        raise Exception('Both arguments must be of the same type')
    return f'{x} + {y} = {x + y}'        

z = my_add_function(1, 1)
# 1 + 1 = 2

a = my_add_function(1, 'chicken')
# Exception: Both arguments must be of the same type

{% endhighlight %}
