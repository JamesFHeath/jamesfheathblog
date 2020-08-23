---
layout: post
title:  "Python Grab Bag: Special Methods"
categories: python programming
tags: python special magic methods dunders
---

# Introduction
[Special Methods](https://docs.python.org/3/reference/datamodel.html#specialnames) in Python, also known as **magic methods** or **dunders**, are methods that allow special syntax to operate on objects. 
Special methods start and end with double underscores, thus the name dunders. 
For example, objects that have a **\_\_len\_\_** method can have the builtin [len()](https://docs.python.org/3/library/functions.html#len) function called on them; objects that have the **\_\_iter\_\_** method can be used in iteration with **for i in object**. 
We're going to go over a couple of implementations, but the options are basically limitless. 

# Addition with Animal Objects
The addition operator can be used on custom objects. 
Let's implement a cat class, and when we **+** a male cat and female cat, we should get a kitten. 

{% highlight python %}
class Cat():
    def __init__(self, gender):
        self.gender = gender
    
    def __add__(self, other):
        # just give the gender of the first Cat
        if self.gender != other.gender:
            return Kitten(self.gender)
        else:
            return None

class Kitten(Cat):
    def __init__(self, gender):
        super(gender)

male_cat = Cat('male')
female_cat = Cat('female')

# Creating a Kitten!
print(male_cat + female_cat)
# <__main__.Kitten object at 0x7fb92d738a90>
{% endhighlight %}


# Iteration over a Tree
Trees are data structures that can be accessed in a variety of ways. 
Let's implement a binary tree, which is a tree with a root and two nodes that are either leaves, empty, or another binary tree. 

{% highlight python %}
# Binary tree implementation, just sticking to integers for simplicity
class IntegerBinaryTree():
    def __init__(self, value, left, right):
        # Nodes can be None or IntegerBinaryTree
        self.value = value
        self.left = left 
        self.right = right
{% endhighlight %}

To iterate through this binary tree, it requires its own **\_\_iter\_\_** and an additional **BinaryTreeIterator** class that itself implements **\_\_iter\_\_** and **\_\_next\_\_**.
Using the **for i in object** syntax, Python will call the iterator's **\_\_next\_\_** method until a **StopIteration** exception is raised. 
When IntegerBinaryTree's **\_\_iter\_\_** method is called, it needs to return an instance of **BinaryTreeIterator**.
BinaryTreeIterator will iterate through instances of IntegerBinaryTree **depth first**, though many implementations are possible. 
Depth first will require a stack, while breadth first requires a queue. 

{% highlight python %}
# BinaryTreeIterator class with the required methods implemented
# I did this from scratch, probably not the best implementation but it works
class BinaryTreeIterator():
    def __init__(self, b_tree):
        self.stack = []
        self.current = b_tree
        
    def __iter__(self):
        return self
    
    def __next__(self):
        if not self.current:
            raise StopIteration
        value = self.current.value
        
        if (left := self.current.left) is not None:
            self.stack.append(self.current)
            self.current = left
        elif (right := self.current.right) is not None:
            self.current = right
        else:
            while True:
                try:
                    if (right := self.stack.pop().right) is not None:
                        self.current = right
                        break
                except IndexError:
                    self.current = None
                    break
            
        return value
        

class IntegerBinaryTree():
    def __init__(self, value, left, right):
        self.value = value
        self.left = left
        self.right = right
        
    def __iter__(self):
        return BinaryTreeIterator(self)
{% endhighlight %}

Now that the iter method is defined, it can be tested with a binary tree. <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;&nbsp;\\<br>
&nbsp;&nbsp;&nbsp;&nbsp;2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;6<br>
&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;\\&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;&nbsp;\\<br>
3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4&nbsp;&nbsp;7&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;9<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\\&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&nbsp;&nbsp;&nbsp;&nbsp;\\<br>
&nbsp;&nbsp;&nbsp;5&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8&nbsp;&nbsp;&nbsp;10&nbsp;&nbsp;&nbsp;11<br>

{% highlight python %}
eleven = IntegerBinaryTree(11, None, None)
ten = IntegerBinaryTree(10, None, None)
nine = IntegerBinaryTree(9, ten, eleven)
eight = IntegerBinaryTree(8, None, None)
seven = IntegerBinaryTree(7, None, eight)
six = IntegerBinaryTree(6, seven, nine)
five = IntegerBinaryTree(5, None, None)
four = IntegerBinaryTree(4, five, None)
three = IntegerBinaryTree(3, None, None)
two = IntegerBinaryTree(2, three, four)
root = IntegerBinaryTree(1, two, six)

for value in root:
    print(value)

# 1
# 2
# 3
# 4
# 5
# 6
# 7
# 8
# 9
# 10
# 11
{% endhighlight %}

