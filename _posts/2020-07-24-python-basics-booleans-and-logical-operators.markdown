---
layout: post
title:  "Python Basics: Boolean and Logical Operators"
categories: python programming
tags: python boolean logical operators
---

### Boolean Introduction
In Python, booleans are a type with two values, *True* or *False*. 
They can be operated on and queried with functions like *if*, *and*, *or*. 
Python also has a sense of *truthy* and *falsey* values, values that will act as true or false when given to if statements. 

### Working with Booleans
Python uses *if*, *elif*, and *else* to execute code based on boolean values. 
*if* and *elif* preceede an expression that evaluates to a boolean value, and execute the code indented below them if the value is True. 
*else* blocks of code will execute if all *if*s and *elif*s failed. 

{% highlight python %}
if True:
    print('True')
elif False:
    print('Won't Print')
else:
    print('Won't Print')
{% endhighlight %}

Python uses the words *and*, *or*, and *not* for logical and, or, and not, as opposed to symbols like &. 
{% highlight python %}
True and True
# True
False or True
# True
not False and True
# True
True and False
# False
{% endhighlight %}

Boolean values can be assigned to variables and returned from functions just like any object. 
{% highlight python %}
true_variable = True
false_variable = False

true_variable and true_variable
# True

false_variable or false_variable
# False

def returns_true():
    return True

returns_true()
# True
{% endhighlight %}

### Truthy and Falsey
Boolean operators can also work on non boolean values. 
Usually *empty* objects will evaluate to False, while objects that aren't empty will evaluate to True. 

* Strings: "" == False, any string over length 0 == True
* Lists: [] == False, any list over length 0 == True
* Integers: 0 == False, any other number is True
* None: None will evaluate to False, this is helpful when testing for any return value

Truthy and falsey values are useful for checking for the existence of objects. 