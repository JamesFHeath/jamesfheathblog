---
layout: post
title:  "Python Grab Bag: Decorators"
categories: python programming
tags: python decorators
---

# Decorators
Decorators in Python are functions that take a function as a parameter, modify its behavior, and return a function.
The returned function could be the same function that was passed in or a completely different function.
Python uses the **@** symbol to decorate function above their definitions, and this is just *syntactic sugar* for redefining the function as the decorator with the function passed as the only argument.
Mutliple decorators can be used by separating them on multiple lines. 
Decorators are easier to understand with examples, let's first define a simple decorator. 
This examples shows a very basic function called *simple_decorator* that takes a single paramter (our *to_decorate* function), prints 'Decorated'!,  and returns *to_decorate*. 
When Python sees the *@simple_decorator*, it actually immediately runs the function *simple_decorator* with *to_decorate* passed as the first parameter; this is why 'Decorated!' prints immediately. 

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

# @simple_decorator is syntactic sugar that translates to:
# to_decorate = simple_decorator(to_decorate)

print(to_decorate())
# To Decorate
# Notice 'Decorated!' is not output at this point
{% endhighlight %}

What if we want to operate on the function when it is called, but not defined?
This is where things get a little more complicated, first with wrapper functions and then decorator factories. 

{% highlight python %}
def decorator_with_wrapper(f):
    def wrapper():
        print('Decorated!')
        f()
    return wrapper

@decorator_with_wrapper
def to_decorate():
    print('To Decorate')
# Notice nothing is printed when decorated
# equivalent to: to_decorate = decorator_with_wrapper(to_decorate)
# This returns the function definition for wrapper, but does not execute it

print(to_decorate())
# Decorated!
# To Decorate
{% endhighlight %}

What if our decorated function takes parameters, how can we access them inside the decorator? 
Recall that wrappers are syntactic sugar for **to_decorate** = **decorator_with_wrapper(to_decorate)**, which will just return the uncalled wrapper function. 
We are calling the wrapper function when we call **to_decorate()**, so if our function takes arguments, then wrapper can take arguments and pass them to our function when it calls **f()**.

{% highlight python %}
def decorator_with_wrapper(f):
# wrapper doesn't need to care what the parameters are for f,
# this will work for any function.
    def wrapper(*args, **kwargs):
        print('Decorated!')
        f(*args, **kwargs)
    return wrapper

@decorator_with_wrapper
def to_decorate(x, y, **kwargs):
    print('To Decorate')
    print(x)
    print(y)
    print(kwargs)

print(to_decorate('searingfrost', 'another parameter', **{'key': 'value'}))
# Decorated!
# To Decorate
# searingfrost
# another parameter
# {'key': 'value'}
{% endhighlight %}

Additional parameters can also be passed to the decorator function itself. 
Decorator factories are the pattern to use in this case. 
Decorator factories will be passed the arguments in the **@decorator** signature, then they will return a normal decorator. 

{% highlight python %}
def decorator_factory(*factory_args, **factory_kwargs):
    def decorator_with_wrapper(f):
        def wrapper(*args, **kwargs):
            print(f'Args Passed to factory: {factory_args}')
            print(f'KeywordArgs passed to factory: {factory_kwargs}')
            print('Decorated!')
            f(*args, **kwargs)
        return wrapper
    return decorator_with_wrapper

@decorator_factory('someargument', a=5, b=10)
def to_decorate(x, y, **kwargs):
    print('To Decorate')
    print(x)
    print(y)
    print(kwargs)
# Syntactic sugar for:
# to_decorate = decoratory_factory('someargument', a=5, b=10)(to_decorate)
# The first call returns decorator_with_wrapper from decorator_factory
# The second call then returns the wrapper function with to_decorate passed in

print(to_decorate('searingfrost', 'another parameter', **{'key': 'value'}))
# Args Passed to factory: ('someargument',)
# KeywordArgs passed to factory: {'a': 5, 'b': 10}
# Decorated!
# To Decorate
# searingfrost
# another parameter
# {'key': 'value'}
{% endhighlight %}

# Conclusion
Decorators are a bit confusing when you first start working with them. 
Play around with the syntax, and follow the chain of execution so you can understand what is happening. 
Decorators are used for tons of purposes, one of my favorite examples is the [**tenacity**](https://pypi.org/project/tenacity/) library, which I wrote about in a [previous blog post]({% post_url 2020-07-31-python-library-tenacity%}).
Another common use case is a logging facility for logging decorated functions and their parameters automatically. 