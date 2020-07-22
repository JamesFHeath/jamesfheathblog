---
layout: post
title:  "Python Basics: Modules"
categories: python programming
tags: python modules import
---

### Modules Introduction
Python *modules* are just files with Python code in them. 
Python modules have the suffix *.py*. 
Definitions in modules can be accessed outside of the module using the *import* keyword. 

### Basic Module
Let's create a Hello, World module. 
Just add *print('Hello, World')* to the file *hello_world.py*

{% highlight python %}
print('Hello, World')
{% endhighlight %}

We can then run this statement from our terminal or command prompt with *python hello_world.py*. 
The Python interpreter *runs from top to bottom every statement in the module*.
Functions and classes are added to the interpreter as definitions, but the internal code is not run unless they are called/instantiated. 

### Importing Modules
If you need code from other modules, it can be *imported*. 
Simply use the import statement followed by the module or package name. 
Standard library modules and packages are always available, such as math, json, and xml. 

{% highlight python %}
import json

# Accessing submodules or specific definitions in a single module is accomplished with *dot* syntax
# json.loads() refers to a function named *loads* in the json module.
# json.loads() takes a JSON string and returns the respective Python object
python_dict = json.loads('{"key": true}')
print(python_dict)
# {'key': True}
{% endhighlight %}

You can import definitions from your own modules as well. 
If the module is in the same directory, you can simply use *import my_module*.
<br>
my_directory
<br>
    |_main.py # import my_module will work here
<br>
    |_my_module.py

{% highlight python %}
# Inside my_module.py
def hello_world():
    print('hello, world')
{% endhighlight %}

{% highlight python %}
# Inside main.py
import my_module

print('hello from inside main py')

my_module.hello_world()
# Will print "hello from inside main py" and then "hello, world" when run
{% endhighlight %}

### Importing with From
You can also import single definitions using the *from* keyword. 
The single definition will then be available in scope. 
You can import wildcard definitions as well, but this is discouraged. 

{% highlight python %}
from json import loads
# loads is now in scope

from json import loads, dumps
# separate multiple definitions with commas

from json import * 
# will import everything from json, discouraged
{% endhighlight %}

### \_\_main\_\_ function
Best practice for a module you want to run directly using the Python interpreter is using a main function.
It's different from some other languages that define a function called main. 
Python checks if the \_\_name\_\_ of the module running is the string '\_\_main\_\_'.
If it is, then it will run the code defined in the if block. 
We can easily add an *if \_\_name\_\_ == '\_\_mainj\_\_'* block to our main.py module. 

{% highlight python %}
# Inside main.py
import my_module

print('hello from inside main py')

if __name__ == '__main__':
    my_module.hello_world()
# Will STILL print "hello from inside main py" and then "hello, world" when run
{% endhighlight %}
