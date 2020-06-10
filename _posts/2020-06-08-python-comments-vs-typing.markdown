---
layout: post
title:  "Python: Comments vs Type Annotations"
categories: python programming 
date: 2020-06-08
tags: python
---

### Comments vs Type Annotations
Working on projects in python, I try to find standards that avoid mistakes like type errors. 
Initially, I added function comments. 
I then went down the road of trying type annotations. 
Ultimately, I came back to function comments because adding and checking types proved more effort than the benefits I reaped. 


### Type Annotations
Python is a dynamically typed language, but they have added the ability to include [type annotations](https://www.python.org/dev/peps/pep-0484/).
Once these annotations are added, you can run a program like [mypy](http://mypy-lang.org/) with your code as input.
This will give you type errors similar to a compiler, but the types are not enforced by the interpreter.
It's up to you to run mypy and find errors. 
This approach became cumbersome for me, and only found simple errors. 
The type checker is of a similar power to Java's, which makes no guarantees about **null** or **none**, which make up the majority of my type errors. 

Example from [PEP 484](https://www.python.org/dev/peps/pep-0484/):
{% highlight python %}
def greeting(name: str) -> str:
    return 'Hello ' + name
{% endhighlight %}

### Comments
Comments are my preferred way to document the types in my program. 
I roughly follow [google's python comment standards](http://google.github.io/styleguide/pyguide.html).
For simple functions, this can be a lot of extra typing, but I find it very helpful to put my function's behavrior into English. 
Additionally, I only need to focus on the structure of the code when I'm reading it;
the comment contains all the type information and meta information that I need, and it's all contained in one place. 
I use the """ docstring comments so that I can generate documentation, another plus for comments.

Example from [PEP 484](https://www.python.org/dev/peps/pep-0484/) with Comments:
{% highlight python %}
def greeting(name):
    """ This functions takes in a name and returns 
    the name prefixed with "Hello"

    Arguments:
        name (str): Name to use

    Returns:
        str: "Hello " plus input name
    """
    return 'Hello ' + name
{% endhighlight %}

### Conclusion
Comments are the way I have gone, though I have only worked on projects where I am the primary coder. 
It could very well be true that for a larger project with multiple coders, type annotations are the way to go.
Either way, use one or the other. 
At the very least, it will make you think about the code you're writing a little bit more. 