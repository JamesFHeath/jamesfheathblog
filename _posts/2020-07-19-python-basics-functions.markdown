---
layout: post
title:  "Python Basics: Functions"
categories: python programming
tags: python functions
---

### Functions Introduction
Functions in Python are the basic building blocks of structure for your programs. 
Python functions organize parts of code together, and allow you to easily run the same code many times. 
Python functions are also **first class citizens**, this means that functions can be treated as any other objects like being assigned to variables or even passed as arguments to other functions. 


### Defining Functions
Functions are defined in Python using the **def** keyword. 
The signature is **def** *my_function_name* (*arg1*, *arg2*, ... *argn*):
The next line will be indented and have your function code. 
Values are returned from functions with the **return** keyword. 
If the **return** keyword is omitted, then a value of None is returned. 

{% highlight python %}
def my_function(arg1, arg2):
    return arg1 + arg2
{% endhighlight %}

### Calling Functions
Functions are called by typing the function name, then open parentheses around the arguments you want to pass in. 

{% highlight python %}
def my_function(arg1, arg2):
    return arg1 + arg2

# Calling my_function
return_value = my_function(1, 1)
print(return_value)
# 2
{% endhighlight %}

### Default Parameters
Function arguments can have defaults, which can be overwritten by the caller. 

{% highlight python %}
def my_function(arg1=1, arg2=2):
    return arg1 + arg2

# Calling my_function using defaults
return_value = my_function()
print(return_value)
# 3

# Calling my_function overwriting defaults
return_value = my_function(4, 5)
print(return_value)
# 9
{% endhighlight %}

### Passing Functions as Parameters
When you reference a function name without parentheses, you can take the function and pass it around. 
For example, you could write a function that takes a function and applies it to every item in a list.

{% highlight python %}
def my_list_mutator(arg_list, arg_function):
    new_list = []
    for arg in arg_list:
        # Function is applied to the items in the list and appended to the new list that is returned
        new_list.append(arg_function(arg))
    return new_list

def my_double_function(x):
    return x * 2

# Passing in my_double_function without parentheses so it's not evaluated
doubled = my_list_mutator([1, 2, 3], my_double_function)
print(doubled)
# 2, 4, 6
{% endhighlight %}

### Lambdas
Lambdas are anonymous functions, functions without names, that can be defined for quick purposes such as list comprehensions. 
They are defined with the lambda ke yword, then parameters, then a colon that defines the return value.
{% highlight python %}
# This lambda function will take an argument, double it, and return the new value
(lambda x: x * 2)
print((lambda x: x * 2)(5))
# 10

# Going back to our list doubling example, it's much nicer with a list comprehension and lambda
doubled = [(lambda x: x * 2) for x in [1, 2, 3]]
print(doubled)
# 2, 4, 6

# This can be made more compact with some syntatic sugar for list comprehensions
doubled = [x * 2 for x in [1, 2, 3]]
print(doubled)
# 2, 4, 6
{% endhighlight %}