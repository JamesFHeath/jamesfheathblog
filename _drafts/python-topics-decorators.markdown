---
layout: post
title:  "Python Topics: Decorators"
categories: python programming
tags: python decorators
---

# Decorators
Decorators in Python are functions that take a function as a parameter, modify its behavior, and return a function. 
The returned function could be the same function that was passed in or a completely different function.   
Python uses the **@** symbol to decorate function above their definitions. 
Mutliple decorators can be used by separating them on multiple lines. 
Decorators are easier to understand with examples, let's first define a simple decorator. 

{% highlight python %}
# Decorators are not defined in a special way, 
# they just need to take and return a function
def simple_decorator(f):
    print('Decorated!')
    return f

@simple_decorator
def to_decorate():
    print('To Decorate')
# Notice that 'Decorated!' prints when to_decorate
# is defined. 

print(to_decorate())
# To Decorate
# Notice 'Decorated!' is not output at this point
{% endhighlight %}

This examples shows a very basic function called *simple_decorator* that takes a single paramter, prints 'Decorated'!,  and returns the parameter. 
When Python sees the *@simple_decorator*, it actually immediately runs the function *simple_decorator* with *to_decorate* passed as the first parameter; this is why 'Decorated!' prints immediately. 
What if we want to operate on the function when it is called, but not defined. 
This is where we can use a wrapper function to our advantage. 

{% highlight python %}
# We define an internal function named wrapper that
# performs our action and executes our parameter f
def decorator_with_wrapper(f):
    def wrapper():
        print('Decorated!')
        f()
    return wrapper

@decorator_with_wrapper
def to_decorate():
    print('To Decorate')
# Nothing is printed at definition time

print(to_decorate())
# Decorated!
# To Decorate
{% endhighlight %}

More parameters can also be passed to decorator functions. 

{% highlight python %}
# Adding parameters x and y
def decorator_with_more_parameters(f, x, y):
    def wrapper():
        print('Decorated!')
        print(f'x = {x}')
        print(f'y = {y}')
        f()
    return wrapper

@decorator_with_more_parameters(x=5, y=10)
def to_decorate():
    print('To Decorate')
# Nothing is printed at definition time

print(to_decorate())
# Decorated!
# To Decorate
{% endhighlight %