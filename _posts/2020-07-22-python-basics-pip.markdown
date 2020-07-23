---
layout: post
title:  "Python Basics: Pip"
categories: python programming
tags: python pip
---

### Pip Introduction
Pip is the default Python package manger.
It allows you to install Python libraries to your computer so they can be imported within your Python code. 

### Installing Pip
Pip will come when you install  [Python](https://www.python.org/downloads/) >= 3.4, but you can also manually install it from [pypl](https://pypi.org/project/pip/).


### Installing 3rd Party Libraries with Pip
Let's try to install a common Python library called [Pandas](https://pandas.pydata.org/).
If you want to find more libraries, [PyPi, the Python Package Index](https://pypi.org/) is the place. 
Once pip is installed on your computer and added to your path, simply run the command:


{% highlight bash %}
pip install pandas
{% endhighlight %}

Updating packages is simple
{% highlight bash %}
pip install --upgrade pandas
{% endhighlight %}

Uninstalling is just as easy
{% highlight bash %}
pip uninstall pandas
{% endhighlight %}

Upgrading pip itself
{% highlight bash %}
pip install --upgrade pip
{% endhighlight %}


### Installing Your Own Packages with Pip
If you have your own package built locally, you simply install it by running pip install on the setup.py directory.
Check my [post about packages]({% post_url 2020-07-22-python-basics-packages %}) for details on creating your own packages.

{% highlight bash %}
pip install /path/to/package/
{% endhighlight %}

### Other Pip Utilities
You can see all your installed libraries with *pip list*.
{% highlight bash %}
pip list

Package                Version      
---------------------- -------------
apturl                 0.5.2        
attrs                  19.3.0       
autopep8               1.5.3        
backcall               0.2.0       
...
{% endhighlight %}

You can also see specifics about a single library, such as version, dependencies, and install location, with *pip show*
{% highlight bash %}
pip show pandas

Name: pandas
Version: 1.0.5
Summary: Powerful data structures for data analysis, time series, and statistics
Home-page: https://pandas.pydata.org
Author: None
Author-email: None
License: BSD
Location: /home/james/.local/lib/python3.8/site-packages
Requires: numpy, pytz, python-dateutil
Required-by: 
{% endhighlight %}


### Requirements.txt
If you're working on a project, especially one with other people, you want to make sure you're all using the same libraries.
*Requirements.txt* files define which libraries your Python project needs. 
You can define package names and versions in requirements.txt, and use pip to install them. 

{% highlight bash %}
requirements.txt
-----------------
pandas==1.0.5
boto3
-----------------

pip install -r requirements.txt
{% endhighlight %}