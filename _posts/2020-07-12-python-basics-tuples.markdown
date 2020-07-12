---
layout: post
title:  "Python Basics: Tuples"
categories: python programming
tags: python tuples
---

### Tuples Introduction
Tuples are one of the basic collections in Python. 
They store objects that are accessible through indexes and iteration. 
Tuples are very similar to lists, except that tuples are immutable. 
Once the value(s) or a tuple are set, they cannot be changed. 
Tuples also have a wonderful property called *unpacking*, which allows easy assignment of tuple values to variables. 

### Creating Tuples
Tuples can be created in 2 ways. 
You can use parentheses and commas, or the tuple function. 

* Using parentheses and commas, you can create tuples anywhere
{% highlight python%}
# t is a tuple of length 3, with two ints and a string
t = (1, 2, 'hello')
# t2 is a tuples of length 0, the empty tuple
t2 = ()
{% endhighlight %}

* Using the tuple function, you can take any iterable and transform it into a tuple

{% highlight python%}
# t is a tuple created from the list l
l = [1, 2, 3]
t = tuple(l)
# t2 is a tuple created from a string, notice it creates a tuple of single length strings
# Note: Python does NOT have characters as a separate class
s = 'hello'
t = tuple(s)
print(t)
# ('h', 'e', 'l', 'l', 'o')
# t_empty is the empty tuple, the tuple function with no arguments
t_empty = tuple()
{% endhighlight %}

### Accessing Tuples
Tuples can be accessed by indexes, iteration, and *tuple unpacking* which will get its own section below.

* Using indexes, tuples can be accessed the same way as lists and other sequences by using square brackets.
{% highlight python%}
t = (1, 2, 3)
t[0]
# 1
# Remember, tuples are immutable, so values cannot be changed. 
t[0] = 77
# ---------------------------------------------------------------------------
# TypeError                                 Traceback (most recent call last)
# ----> 1 t[0] = 15
# TypeError: 'tuple' object does not support item assignment
{% endhighlight %}

* Tuples can be iterated through with a for loop.
{% highlight python%}
t = (1, 2, 3)

for x in t:
    print(x)
# 1
# 2
# 3
{% endhighlight %}

### Tuple Unpacking
Tuple unpacking is the ability for tuples to be "disassembled" into compontents and assigned to variables.
All you need to do is comma separate the variables you want to assign the tuple pieces to, then set them equal to the tuple.
{% highlight python%}
# Simple example
t = (1, 2, 3)
x, y, z = t
print(x)
# 1
print(y)
# 2
print(z)
# 3
{% endhighlight %}

Tuple unpacking is incredibly useful for returning multiple values from functions in a simple way. 
{% highlight python%}
# Let's say we want to generate a random number using a seed, we can return
# both the random int and the seed so that the process can be repeated
import random 

seed = 17

def get_random_int(seed):
    random.seed(seed)
    random_int = random.randint(0, 10) # returns an int from 0 to 10
    return (random_int, seed)

random_int, seed_used = get_random_int(seed)
{% endhighlight %}

Tuple unpacking is also used with the built-in *enumerate* function, that iterates through a sequence giving both an index and the value.
{% highlight python%}
my_list = ['hello', 'tuple', 'unpacking']

for i, v in enumerate(my_list):
    print(f'Index {i} is {v}')
# Index 0 is 'hello'
# Index 1 is 'tuple'
# Index 2 is 'unpacking'
{% endhighlight %}

### Named Tuples
Tuples are very useful for returning multiple values from a function, but sometimes indexes are not clear. 
Namedtuples are part of the *collections* library built in to Python. 
Namedtuples allow us to name the different values of our tuple for easier understanding.
{% highlight python%}
from collections import namedtuple

HttpResponse = namedtuple('HttpResponse', ['code', 'message'])

def call_dummy_server():
    return HttpResponse(200, 'Server responsed with success')

# namedtuple can still be used for tuple unpacking
my_code, my_message = call_dummy_server()

# Or you can access values by name with dot notation
my_server_response = call_dummy_server()
print(my_server_response.code)
# 200
print(my_server_response.message)
# 'Server responded with success'
{% endhighlight %}


