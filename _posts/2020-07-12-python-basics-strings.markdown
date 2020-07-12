---
layout: post
title:  "Python Basics: Strings"
categories: python programming
tags: python strings
---

### Strings Introduction
Python strings are one of the builtin classes of Python. 
They are immutable sequences (like tuples) but always contain Unicode. 
Unlike other languages, Python has no concept of characters. 
A "character" in Python is just a string of length 1. 

### Creating Strings
Strings can be created as string literals or using the builtin str function. 
* String literals are surrounded with single quotes ', double quotes ", or 3 single ''' or 3 double quotes """.
{% highlight python%}
s = 'hello'
s2 = "hello"
s3 = '''hello'''
s4 = """hello"""
# All equivalent
{% endhighlight %}

* The *str* function takes any object and returns a string. 
Technical Note: It first tries to call the object's .\_\_string\_\_() method, then the .\_\_repr\_\_() method.
{% highlight python%}
int_five = 5
# 5
string_five = str(5)
# '5'
my_dictionary = {'my_key': 55}
string_dictionary = str(my_dictionary)
# "{'my_key': 55}"
{% endhighlight %}


### Accessing Elements
String elements are accessed exactly like lists. 
You can use square brackets to access single indexes and slices.
Iteration is also builtin for strings.
See my [list blog post]({% post_url 2020-07-03-python-basics-lists%}) for details.

### String Methods
Strings have tons of builtin methods, I'm going to touch on a few of the ones I most commonly use.
See the [documentation](https://docs.python.org/3/library/stdtypes.html#str) for a full list of methods.
* *Concatenation* is simply putting two strings together to create a new string. 
Just use the + operator to use this method. 
{% highlight python%}
s1 = 'hello '
s2 = 'world'
s3 = s1 + s2
print(s3)
# 'hello world'
{% endhighlight %}

* The *replace* method replaces instances of a search string with a replacement string and returns a new string. 
{% highlight python%}
s1 = 'SearingFrost'
s2 = s1.replace('Frost', 'Fire')
print(s2)
# 'SearingFire'
{% endhighlight %}

* The *split* method splits a string based on a given delimiter, such as a comma, a returns a list of the strings.
{% highlight python%}
s1 = 'Searing, Frost, Fire'
l = s1.split(',')
print(l)
# ['Searing', 'Frost', 'Fire']
{% endhighlight %}


### String Formatting
String formatting is a method, but I believe it deserves its own section. 
I'm going to be using the *f* string formatting.
Though there are other ways to format strings, this is the best one in my opinion.
To create an *f string*, or format string, simply add a lowercase f before the first quotaion. 
You can then use curly brackets to surround ANY Python expression you want evaluated as a string. 
This is known as interpolation.
I use f strings almost every time I use strings. 
{% highlight python%}
sf = 'Searing Frost'
f_string = f'Hello, my name is: {sf}'
print(f_string)
# 'Hello, my name is Searing Frost'

expression_string = f'1 + 1 = {1 + 1}'
print(expression_string)
# '1 + 1 = 2'
{% endhighlight %}