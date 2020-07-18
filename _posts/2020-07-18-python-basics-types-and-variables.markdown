---
layout: post
title:  "Python Basics: Types and Variables"
categories: python programming
tags: python variables types
---

### Python Variables and Types
Python is an interpreted language, which means that Python programs are not compiled before they are run. 
This leads to a **dynamic** type system. 
Dynamic type systems figure out the type of a variable at runtime, as opposed to compile time. 
This is in contrast to static type systems that figure out the type of a variable at compile time. 
Dynamic languages include Python and Javascript, and static languages would include Java and C++. 
Dynamic and static are different from strongly typed languages and weakly typed languages. 
Python is more strongly typed, which means it does not try to automatically cast variables to different types. 
Javascript is weakly typed, it will attempt to figure out a compatible type with almost any variable. 
These definitions are not rigid, and there is gradient between dynamic/static and strong/weak. 

### Setting Variables in Python
Variables in Python are set with the **=** operator. 
Python figure out the type of a variable at runtime, so there is no need to add any type to variables like in some other languages.
Once a variable is set, there is no restriction to setting a new value to the same variable. 
{% highlight python%}
x = 5
# x is now assigned the value 5
x = 'hello'
# x is now assigned the str value "hello"
x = 1.0
# x is now assigned the float value 1.0
{% endhighlight %}

### Type Function
The builtin **type** function is a critical piece of your Python toolbox. 
It will tell you the type of any variable. 
{% highlight python%}
x = 5
type(x)
# int
s = 'hello'
type(s)
# str
def my_function():
    return 'SearingFrost'

type(my_function)
# function
type(my_function())
# str
{% endhighlight %}

### Id Function
A very useful tool is the builtin **id** function. 
It takes a variable and returns the id of its memory location. 
You can use this to compare different variables to see if they are pointing to the same memory. 
Primitives like ints and *None* are special, in that they have their own memory location that's loaded and can't be overwritten. 

{% highlight python%}
l1 = [1, 2, 3]
l2 = l1
id(l1) == id(l2)
# True because they are pointing to the same memory, and change to one changes the other

d1 = {'key': True}
d2 = {'key': True}
id(d1) == id(d2)
# False even though the values are the same, the memory location is different

x = 5
y = 5
id(x) == id(y)
# True because they are pointing to the same primite object
{% endhighlight %}
