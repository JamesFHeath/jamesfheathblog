---
layout: post
title:  "Python Basics: Dictionaries"
categories: python programming
tags: python dictionaries dicts
---

### Dictionaries Introduction
Dictionaries, or dicts, are a key-value collection in Python. 
Using just dicts, you can get a long way writing Python code. 
Dicts can hold objects of any type as values, but the keys have to be "hashable". 
This just means that they need to be immutable; strings or integers or even tuples can be keys, but lists and other dicts cannot. 
In practice, you're mostly going to use strings as keys. 

### Creating Dicts
Dicts are created in 3 common ways, much like lists. 
* Using curly brackets {}, you can separate keys and values with colons, and pairs of values with commas. 
{% highlight python%}
# Keys are separated from their values with ':' and pairs are separated by ','
d = {'key': 'value', 'another_key': 'another_value'}
{% endhighlight %}
* Using the built-in dict function, you can pass a mapping, two iterables, a list of pairs, etc.  
{% highlight python%}
# Passing keys and values as kwargs
d = dict(key1='value1', key2='value2', key3='value3')
# Passing two lists combined using the zip function
key_list = [1, 2, 3]
value_list = [True, True, False]
d = dict(zip(key_list, value_list))
# Passing another dict or mapping
d2 = dict(d)
# Passing a list of two-tuples
tuple_d = dict([('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3')])
{% endhighlight %}
* Using dictionary comprehensions. Dictionary comprehensions are used less than list comprehensions, but are sometimes the right tool
{% highlight python%}
# Creates a dict with keys 0..9 and all 1's for values
dict_comprehension = {x: 1 for x in range(10)}
{% endhighlight %}

### Adding Values to Dicts
You can add values to dicts with square brackets or the *update* method. 
Using square brackets, you specify a key and *=* to define the value of that key.
{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
d['3rd Key'] = True
print(d)
# {'my_key': 'my_value', 'my_other_key': 'my_other_value', '3rd Key': True}
d['my_key'] = 'new value'
print(d)
# {'my_key': 'new value', 'my_other_key': 'my_other_value', '3rd Key': True}
{% endhighlight %}

Using the *update* method, you can add values to your dict with the same arguments the dict function takes. 

{% highlight python%}
d = dict(key1='value1', key2='value2', key3='value3')
d.update(key4='value4')
print(d)
# {'key1': 'value1', 'key2': 'value2', 'key3': 'value3', 'key4': 'value4'}
{% endhighlight %}

### Accessing Values in Dicts
Dict values can be accessed using key names. 
You can use square brackets just like with lists, but instead of putting in the index, you put in the key. 

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
d['my_key']
# my_value
{% endhighlight %}

If the key is not present, you will get a KeyError. 

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
d['my_missing_key']
# KeyError
{% endhighlight %}

To avoid this, you can use the *get* method. 
It will either return None, or a default value you specify.

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
d.get('my_missing_key')
# None
d.get('my_missing_key', 'key missing!!!!')
# key missing!!!!
{% endhighlight %}

### Iteration with Dicts
The *in* operator can be used to access the keys of a dict. 
This way, you can access all the values of your dict. 

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
for k in d:
    print(d[k])
# my_value
# my_other_value
{% endhighlight %}

If you want to access the keys AND values, you can use the items method. 

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
for k, v in d.items():
    print(k)
    print(v)
# my_key
# my_value
# my_other_key
# my_other_value
{% endhighlight %}

### Other Niceties
To remove values from dicts, you can either use the *del* keyword, or the *pop* method.

{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
del d['my_key']
print(d)
# {'my_other_key': 'my_other_value'}
d.pop('my_other_key')
print(d)
# {}
{% endhighlight %}

To see if a key exists, you can use the *in* operator. 
{% highlight python%}
d = {'my_key': 'my_value', 'my_other_key': 'my_other_value'}
'missing_key' in d
# False
'my_key' in d
# True
{% endhighlight %}

### Default Dicts Bonus
Default dicts are subclasses of dictionaries that contain default values. 
They are defined with a type, such as *list* or *int*. 
When you access keys, if they key does not exist the value defaults to the empty constructor of the type passed in. 
For example, if you want a dict of lists you want to append to, you can always use the append method even if the key does not exist yet. 

{% highlight python%}
from collections import defaultdict

dd = defaultdict(list)
dd['new'].append(1)
dd['new'].append(2)
print(dd)
# defaultdict(<class 'list'>, {'new': [1, 2]})
{% endhighlight %}

Another use case is with counters. 
If you want to count the appearances of items in a list, you can create a defaultdict of int.

{% highlight python%}
from collections import defaultdict

word_list = ['Python', 'Blog', 'Python', 'Python', 'Dict', 'Dict']
count_dict = defaultdict(int)

for word in word_list:
    count_dict[word] += 1
# defaultdict(<class 'int'>, {'Python': 3, 'Blog': 1, 'Dict': 2})
{% endhighlight %}