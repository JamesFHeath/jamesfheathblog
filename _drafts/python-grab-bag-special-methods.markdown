---
layout: post
title:  "Python Grab Bag: Special Methods"
categories: python programming
tags: python special magic methods dunders
---

# Introduction
[Special Methods](https://docs.python.org/3/reference/datamodel.html#specialnames) in Python, also known as **magic methods** or **dunders**, are methods that allow special syntax to operate on objects. 
Special methods start and end with double underscores, thus the name dunders. 
For example, objects that have a __len__ method can have the builtin [len()](https://docs.python.org/3/library/functions.html#len) function called on them; objects that have the __iter__ method can be used in iteration with **for i in object**. 