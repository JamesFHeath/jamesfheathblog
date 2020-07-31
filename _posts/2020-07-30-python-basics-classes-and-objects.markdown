---
layout: post
title:  "Python Basics: Classes and Objects"
categories: python programming
tags: python classes objects
---

### Introduction
Python is an object-oriented languge with all the standard class features like inheritance, instantition, and methods. 
Python defines classes in a flexible and simple way. 
Unlike Java/C++, all class members are public and class definitions are easily mutated at runtime. 
This post assumes some familiarity with object oriented concepts, and will give some examples in Java as well to illustrate Python differences. 

### Defining a Class
Classes are defined with the **class** keyword. 
After the colon, any statements will be added as attribute to the class. 
Variables and function are conventional, but any statement is allowed. 
Class attributes can be accessed with dot syntax.
Additional attributes can be added at any time with dot syntax as well.

{% highlight python %}
# MyClass does nothing 
class MyClass:
    pass

# TwoAttrClass contains 2 attributes, the variable x and the function f
class TwoAttrClass:
    x = 'Two Attribute Class Variable'
    # We will come back to the self parameter soon
    def f(self):
        return 'Two Attribute Class Function'

print(TwoAttrClass.x)
# Two Attribute Class Variable
print(TwoAttrClass.f())
# Two Attribute Class Function

TwoAttrClass.y = 'Extra Attribute'
print(TwoAttrClass.y)
# Extra Attribute
{% endhighlight %}

### Creating Objects
Objects can be created by calling a class name just like a function, with parentheses. 

{% highlight python %}
class MyClass:
    pass

# my_object is an object of type MyClass
my_object = MyClass()

print(my_object)
# __main__.MyClass object at 0x... (memory location)
{% endhighlight %}

### \_\_init\_\_ method, object methods, and self
To perform setup on a newly created object, define an \_\_init\_\_ method inside the class definition. 
\_\_init\_\_ methods are Python's constructors.
When a class with an \_\_init\_\_ function is instantiated, the \_\_init\_\_ method is automatically called with the parameters passed in. 
Methods are functions that are attached to object instances. 
The first parameter of a method, **self** by convention, is the object instance. 

{% highlight python %}
class InitClass:
    x = 1
    y = 2
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

# self is passed in automatically
init_object = InitClass(x=3, y=4, z=5)

print(init_object.x)
# 3 that was passed in on initialization
print(init_object.y)
# 4 that was passed in on initialization
print(init_object.z)
# 5 that was passed in on initialization

print(InitClass.x)
# Still 1
print(InitClass.y)
# Still 2
print(InitClass.z)
# Attribute error because z only belongs to the object instance and not the class
{% endhighlight %}

Java hides the **this** parameter within constructors and method signatures. 

{% highlight java %}
public class MyClass{
    int x;
    int y;

    public MyClass(*this*, x, y) {
        this.x = x;
        this.y = y;
    }
}
{% endhighlight %}

{% highlight python %}
class ClassWithMethod:
    def my_method(self):
        return f'method called with object: {self}'

object_with_method = ClassWithMethod()

# Type is method
print(object_with_method.my_method)
# <bound method ClassWithMethod.my_method of <__main__.ClassWithMethod object at 0x1035a12e0>>

# When called from an object instance, the object is passed in silently
print(object_with_method.my_method())
# 'method called with object: <__main__.ClassWithMethod object at 0x1022db250>'

# Equivalent to calling the class's method and passing in the object as a parameter
print(ClassWithMethod.my_method(object_with_method))
# 'method called with object: <__main__.ClassWithMethod object at 0x1022db250>'
{% endhighlight %}

### Inheritance
Inheritance is used to create a derived class with the properties of its base or parent class. 
In Python, inherited classes are added to the class signature. 

{% highlight python %}
class BaseClass:
    pass

# DerivedClass inherits from BaseClass
class DerivedClass(BaseClass)
    pass
{% endhighlight %}
 
Use **isinstance(object, class)** to check if an object is an instance of class or if class is one of its ancestors. 

{% highlight python %}
class BaseClass:
    pass

class DerivedClass(BaseClass)
    pass

d = DerivedClass()

print(isinstance(d, DerivedClass))
# True
print(isinstance(d, BaseClass))
# Also True
{% endhighlight %}

Class inheritance can also be checked with **issubclass(derived_class, base_class)**. 

{% highlight python %}
class BaseClass:
    pass

class DerivedClass(BaseClass)
    pass

print(issubclass(DerivedClass, BaseClass))
# True
{% endhighlight %}

Derived classes receive all the attributes of their base class. 
Any attribute can be overwritten by the derived class with no restrictions. 
Attributes are first searched for in the derived class, and then to the bases class and so on. 
Use **super** to explicitly call the base class. 

{% highlight python %}
class BaseClass:
    base_attribute = 'base attribute value'

    def __init__(self, x):
        self.x = x    

class DerivedClass(BaseClass)
    # Override __init__ from BaseClass
    def __init__(self, x, y):
        # Call to BaseClass __init__
        super().__init__(x)
        self.y = y

derived_object = DerivedClass(x=1, y=2)

print(derived_object.x)
# 1
print(derived_object.y)
# 2
print(derived_object.base_attribute)
# base attribute value
{% endhighlight %}

{% highlight python %}
class BaseClass:
    def __init__(self, x):
        self.x = x    

class DerivedClass(BaseClass)
    def __init__(self, x, y):
        self.x = x    
        self.y = y

derived_object = DerivedClass(x=1, y=2)

print(derived_object.x)
# 1
print(derived_object.y)
# 2
print(derived_object.base_attribute)
# base attribute value
{% endhighlight %}

Python also supports multiple inheritance. 
Separate the base classes with commas when defining the derived class. 

{% highlight python %}
class BaseClassA:
    pass

class BaseClassB:
    pass

# Derived from both A and B
class DerivedClassAB(BaseClassA, BaseClassB)
    pass
{% endhighlight %}

### Private Fields
Java and other languages have private fields that can only be accessed from inside the class. 
Python has no restrictions on access, so by convention if you don't want a client using a field or method you should prefix its name with an underscore. 

{% highlight python %}
class PrivateClass:
  _x = 'private by convention'

{% endhighlight %}

### Static Methods
Static methods are methods that belong to the class but not any specific instantiation. 
Python uses the **@staticmethod** decorator to define a static method, the equivalent of the static keyword in Java. 

{% highlight python %}
# TwoAttrClass contains 2 attributes, the variable x and the function f
class StaticMethodClass:
    # notice no self parameter for the static method 
    @staticmethod
    def f():
        return 'I belong to the class'

print(StaticClassMethod.f)
# <function StaticMethodClass.f at 0x... memory location

o = StaticMethodClass()
print(o.f)
# <function StaticMethodClass.f at 0x... memory location
# Function, not method like above
{% endhighlight %}