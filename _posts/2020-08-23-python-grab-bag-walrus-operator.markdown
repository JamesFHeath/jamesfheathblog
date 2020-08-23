---
layout: post
title:  "Python Grab Bag: Walrus Operator"
categories: python programming
tags: python walrus operator assignment expression
---

### Walrus Operator
[Assignment expressions](https://www.python.org/dev/peps/pep-0572/), fondly called the **walrus operator**, is a new operator in **Python 3.8** that allows assigning the result of expressions to variables. 
***variable* := *expr*** can be placed anywhere an expression can be placed. 
The purpose of the walrus operator is to save the results of expressions that are going to be used in the future. 
Be sure to wrap the assignment expression in parenthesis if there is any ambiguity about what value is being assigned. 

### Examples
#### Checking Values in a Dictionary
This first example will be checking if an object is in a dictionary, then using the value if it is in the dictionary. 

{% highlight python %}
my_dict = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}

# Traditional way
if 'key1' in my_dict:
    value = my_dict['key1']
    print(value)
    # do some work with value...

# Walrus Operator
# get returns None if the value is not found
if value := my_dict.get('key1'):
    print(value)
    # do some work with value...
{% endhighlight %}

If the value associated with the key needs to be checked, use parenthesis around the assignment expression.
Otherwise, the value being assigned will be the boolean expression and not the result of getting the key.  

{% highlight python %}
my_dict = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}

test_value = 'value1'

# Traditional way
if my_dict.get('key1') == test_value:
    value = my_dict['key1']
    print(value)
    # do some work with value...

# Walrus Operator
if (value := my_dict.get('key1')) == test_value:
    print(value)
    # do some work with value...
{% endhighlight %}

#### Reading Streams
A stream, such as a file, may need to be read n bytes at a time without knowing the full length.
This can be accomplished with a while loop, but it's much simpler with the walrus operator. 

{% highlight python %}
def process_bytes(b):
    print(b)

# This file has some number of bytes of text on a single line
# We want to read 10 bytes at a time and then process them in some way


# Traditional way
my_file = open('my_file.txt')

read_bytes = my_file.read(10)
while read_bytes: 
    process_bytes(read_bytes)
    read_bytes = my_file.read(10)

my_file.close()


# Walrus Operator
my_file = open('my_file.txt')

# Much simpler and easier to understand
while read_bytes := my_file.read(10): 
    process_bytes(read_bytes)

my_file.close()
{% endhighlight %}

### Conclusion
The walrus operator can make a lot of code easier to write. 
Keep it in mind when you're writing something new or going back and refactoring.  
Be sure that you are using Python 3.8, as it's not valid in previous versions. 