---
layout: post
title:  "Python Basics: Modules and Packages"
categories: python programming
tags: python modules
---

### Modules and Packages Introduction
Python *modules* are just files with Python code in them. 
Python modules have the suffix *.py*. 
Definitions in modules can be accessed outside of the module using the *import* keyword. 
<br>
Python *packages* are just a folder containing Python modules. 
Python packages just require an __init__.py file, often blank, inside of them to be recognized as a package. 
You can think of packages as a level up of organization from modules. 
Packages can even contain subpackages. 

### Basic Module
Let's create a Hello, World module. 
Just add *print('Hello, World')* to the file *hello_world.py*

{% highlight python %}
print('Hello, World')
{% endhighlight %}

We can then run this statement from our terminal or command prompt with *python hello_world.py*. 
The Python interpreter runs from top to bottom every statement in the module.
Functions and classes are added to the interpreter as definitions, but the internal code is not run unless they are called/instantiated. 

### __main__ function
