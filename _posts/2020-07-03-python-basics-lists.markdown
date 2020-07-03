---
layout: post
title:  "Python Basics: Lists"
categories: python programming
tags: python lists 
---

### Lists Introduction
Lists are one of the basic collections in Python. 
They store objects that are accessible through indexes and iteration. 
Unlike some other languages, like Java, Python lists do not need to contain items that share a type. 
Python lists are mutable, and the length can be changed and does not need to be set. 
The flexibility of Python lists are their strength, but you do lost some of the speed of C/C++ arrays.  

### Creating Lists
Lists can be created in 3 ways.
* Using square brackets, lists can be defined simply by their contents.
{% highlight python%}
# x is a list of length 3, with two ints and a string
x = [1, 2, 'hello']
# y is a list of length 0, the empty list
y = []
{% endhighlight %}

* With the [builtin *list* function](https://docs.python.org/3/library/functions.html#func-list), you call list([iterable])
{% highlight python%}
# z_error will generate a syntax error, because two integers and a string are not an iterable
z_error = list(1, 2, 'hello')
# TypeError: list expected at most 1 argument, got 3
# Iterables can be any sequence that implements iterable
z_from_x = list(x)
z_from_brackets = list([1, 2, 'hello'])
# Even range will work!
z_from_range(range(10))
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
# Empty list can be created too
z_from_y = list(y)
z_from_no_args = list()
{% endhighlight %}

* List comprehensions are the most advanced way to create lists, but they are very powerful. 
You can use any iterable with a list comprehension, and you operate on each item of the iterable with a function to generate the list.
{% highlight python%}
# Here we take the numbers 0..9 from range(10) and square them to get a new list
zero_to_nine_squared = [x**2 for x in range(10)]
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
# We can use any function in place of the exponential function, this function just ignores x and returns all 1s
ten_ones = [(lambda x : 1)(x) for x in range(10)]
# [1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
{% endhighlight %}

### Indexes
The simplest way to access items in a list is through the items' index. 
Lists are indexed using square brackets with an integer inside. 
Lists in Python are 0 indexed, so the first element will be referred to by 0. 
You can also separate two integers indexes with a colon to get a **slice** from the first integer to one below the second integer.
Because lists are mutable, you can change the value of an item by getting its index and assigning a new value.

{% highlight python%}
index_list = [1, 2, 3, 4, 5]
# First value is 1
value_of_one = index_list[0]
# A slice can be a bit confusing, 1 refers to 2, and it creates a slice up to but not including index 4.
# One way of remember this is to start at the first value, and generate a list of 4 -1 = 3
list_from_2_to_4 = index_list[1:4]
# This replaces the 0th index, the value 1, with the value 77
mutate_by_index = [1, 2, 3, 4, 5]
mutate_by_index[0] = 77
# [77, 2, 3, 4, 5]
{% endhighlight %}

### List Methods
Like everything else in Python, lists are objects and have methods that operate on them. 
Python lists implement everything from [common sequence](https://docs.python.org/3/library/stdtypes.html#typesseq-common) and [mutable sequence](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable). 
The most common methods I use are append and extend. 
Append adds a single item to a list, and extend adds the contents of another list to your original list. 

{% highlight python%}
append_list = [1, 2, 3]
append_list.append(4)
# [1, 2, 3, 4]
append_list.extend([5, 6, 7])
# [1, 2, 3, 4, 5, 6, 7]
{% endhighlight %}

There are many other methods that can be used, like copy, pop, reverse, and remove. 
The [official standard types documentation](https://docs.python.org/3/library/stdtypes.html) is the best place to look.  

### Iteration
Iteration is a wonderful way to access every element in a list and do "something". 
Python allows iteration using the "for x in list" syntax. 
This will return every item in your list, assign it to x, and allow you to operate on it. 

{% highlight python%}
# This will just print 1, 2, and 3 on separate lines. 
for x in [1, 2, 3]:
    print(x)
{% endhighlight %}

### Other Niceties
* Python's [builtin *len* function](https://docs.python.org/3/library/functions.html#len) will return the length of any , it's incredibly useful. 
{% highlight python%}
my_list = [1, 7, 'goodbye']
# 3
len(my_list)
{% endhighlight %}

* The *in* operator. If you want to know if an item is in a list, you can just use "x in list" and get a boolean back.
{% highlight python%}
search_value = 'SearingFrost'
search_value in ['SearingFrost', 'NotSearingFrost', 1, 2, 3]
# True
{% endhighlight %}




