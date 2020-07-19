---
layout: post
title:  "Python Basics: Files"
categories: python programming
tags: python files
---

### Files Introduction
Python has a ton of great utilities for working with files, especially text files. 
We're going to go over the basics of reading from files and writing to files in this post. 


### Reading from Files
Reading from files in Python is very easy using the **with** keyword. 
**With** lets Python take care of the business of opening and closing our files, and we can just focus on getting our work done. 
The **open** function takes a file path and opens the file for you in the **with** context. 

{% highlight python %}
with open('my_file.txt') as my_file:
    # We create the my_file object and operate on it in this indented block
    file_contents = my_file.read()

print(file_contents)
# Will output the contents of the file
{% endhighlight %}

There are several ways to read the contents of a file, the most common will be the file.read() method and iteration. 

{% highlight python %}
with open('my_file.txt') as my_file:
    # my_file.read() will read all the contents of the file and assing it to the variable file_contents
    file_contents = my_file.read()

with open('my_file.txt') as my_file:
    # We can also iterate line by line with a for loop
    for line in my_file:
        print(line)
    # This will print each line of the file
{% endhighlight %}

### Writing to Files
Writing to files is just as easy in Python using the **with** keyword. 
You just need to specify in the **open** function that you want to write to the file with the mode argument. 
Check the [open function documentation](https://docs.python.org/3/library/functions.html#open) for all the modes. 

{% highlight python %}
# Specifying 'w' as the mode means write, it defaults to read only 'r'
with open('my_file.txt', mode='w') as my_file:
    my_file.write('SearingFrost')

with open('my_file.txt') as my_file:
    searing_frost = my_file.read()

print(searing_frost)
# SearingFrost
{% endhighlight %}
