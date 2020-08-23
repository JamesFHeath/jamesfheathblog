---
layout: post
title:  "Python Basics: Sets"
categories: python programming
tags: python sets
---


### Sets Introduction
Sets in Python are **unordered** collections of objects. 
They are very similar to [mathematical sets](https://en.wikipedia.org/wiki/Set_(mathematics)), especially in that there are no repeat objects and set operations like union and intersection are implemented. 
One of the best use of sets is to remove duplicates from other collections by turning them into sets. 
The simple set operations can also be very helpful, but if you need something more complex look into [pandas](https://pandas.pydata.org/). 

### Creating Sets
Sets can be created in two ways, with curly brackets or the built in set function. 
* Using curly brackets {}, you can separate objects with commas
{% highlight python%}
{1, 2, 3, 'a', 'b', 'c'}
{% endhighlight %}
* The builtin **set** function will create a set out of an iterable object. 
{% highlight python%}
my_list = [1, 2, 3, 'a', 'b', 'c']
my_set = set(my_list)
{% endhighlight %}

### Common Operations
All the basic operations for collections in Python work on sets. 
**len(set)**, **x in set**, **x not in set** work just like lists or other collections.
Adding to sets can be done with the **add(elem)** method or the **update(*other_sets*)** method.
Removing objects can be done with the **remove(elem)** method, the **discard(elem)** method, the **pop()** method, or the **clear()** method.

{% highlight python%}
set_ints = {1, 2, 3}
set_strings = {'hello', 'searing', 'frost'}
mixed_set = {1, 'hello'}

# len
print(len(set_ints))
# 3

# in operator
print(1 in set_ints)
# True

# add(elem) method
set_ints.add(4)
print(set_ints)
# {1, 2, 3, 4}

# update(other_sets)
set_ints.update(mixed_set)
print(set_ints)
# {1, 2, 3, 4, 'hello'}

# remove(elem)
set_ints.remove(4)
print(set_ints)
# {1, 2, 3, 'hello'}
# KeyError if we try to remove(4) again
set_ints.remove(4)
# KeyError: 4

# discard(elem)
# Works the same as remove, but does not raise KeyError if element not in set
set_ints.discard(4)
# No KeyError
print(set_ints)
{1, 2, 3, 'hello'}

# pop()
# Just remove an element and returns it
print(set_ints.pop())
# 1
print(set_ints)
# {2, 3, 'hello'}
{% endhighlight %}

### Set Operations
* Union: **|** operator, returns all elements from 2 sets. Like a SQL full outer join.
* Intersetsion: **&** operator, returns common elements from 2 sets. Like a SQL inner join.
* Difference: **-** operator, returns elements from first set that aren't in the second set. Like a SQL left only join.
* Symmetric Difference: **^** operator, returns elements in 1 set but not both. Like SQL full outer join minus an inner join.

{% highlight python%}
set_ints = {1, 2, 3}
set_strings = {'hello', 'searing', 'frost'}
mixed_set = {1, 'hello'}

# Union
print(set_ints | set_strings)
# {1, 2, 3, 'frost', 'hello', 'searing'}

print(set_ints | mixed_set)
# {1, 2, 3, 'hello'} 
# Notice 1 is only present a single time, because sets don't contain duplicates

# Intersection
print(set_ints & set_strings)
# set()
# Empty set

print(set_strings & mixed_set)
# {'hello'}
# 'hello' is the only common element

# Difference
print(set_strings - set_ints)
# {'frost', 'hello', 'searing'}
# Everything returned, notice order is not preserved

print(set_strings - mixed_set)
# {'frost', 'searing'}
# 'hello' excluded because it's a memeber of mixed_set

# Symmetric Difference
print(set_string ^ set_ints)
# {1, 2, 3, 'frost', 'hello', 'searing'}
# Every member in new set

print(set_strings ^ mixed_set)
# {1, 'frost', 'searing'}
# Only members in 1 set but not both, 'hello' exluded

print(set_ints ^ mixed_set)
# {2, 3, 'hello'}
{% endhighlight %}

### Frozen Sets
Briefly, [Frozen Sets](https://docs.python.org/3/library/stdtypes.html#frozenset) are just sets that cannot be modified once they are created. 
This is useful when you want to guarantee immutability. 