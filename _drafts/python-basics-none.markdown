---
layout: post
title:  "Python Basics: None"
categories: python programming
tags: python none null
---

# None
None is a Python object representing no value. 
None works much in the same way as null in other languages. 
When a Python interpreter starts up, it sets None to a single memory location, meaning there is only a single None in Python. 
None cannot be overwritten by a user. 

# Working with None
None has a *falsey* value, so boolean operators will work well with it. 
Often, it is important to check if a return value exists before operating on it. 

{% highlight python %}
my_dictionary = {'key': 'value'}

my_dictionary.get('key')
# value
my_dictionary.get('key2')
# None
{% endhighlight %}