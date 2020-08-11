---
layout: post
title:  "Python Topics: Virtual Environments"
categories: python programming
tags: python virtual environments
---

# Introduction
Python [virtual environments](https://docs.python.org/3/tutorial/venv.html) are a way of isolating specific Python libraries for a project. 
Virtual environments have their own Python interpreter, pip, and installed libraries. 
Virtual envrionments can be activated and deactivated on the command line or terminal to work on projects that need certain library versions. 

# Creating a Virtual Envrionment
Virtual environments can be created anywhere on the file system, a reasonable location is an **venvs** directory in your home directory (~/env/*virtualenvironments*).
Let's change to our **~/venvs** directory and create a virtual environment named "searing-frost". 

{% highlight bash %}
~$ cd ~/venvs
~/venvs$ python3 -m venv searing-frost
~/venvs/searing-frost$ cd searing-frost
~/venvs/searing-frost$ ls
bin  include  lib  lib64  pyvenv.cfg  share
{% endhighlight %}

# Activating and Deactivating Virtual Environments
The **bin** directory contains the script to activate the virtual environment. 

{% highlight bash %}
~/venvs/searing-frost$ source ./bin/activate

Windows: searing-frost\Scripts\activate.bat
{% endhighlight %}

Once the virtual environment is activated, the terminal will show (searingfrost) on the prompt.

{% highlight bash %}
(searing-frost)~/venvs/searing-frost$
{% endhighlight %}

To leave the virtual environment, just use **deactivate**

{% highlight bash %}
(searing-frost)~/venvs/searing-frost$ deactivate
~/venvs/searing-frost$
{% endhighlight %}

# Installing and Packaging Libraries in Virtual Environments
The virtual environment has its own pip that you can use to install libraries. 
Let's see what's installed by default with **pip list**. 

{% highlight bash %}
(searing-frost)~/venvs/searing-frost$ pip list

Package       Version
------------- -------
pip           20.0.2 
pkg-resources 0.0.0  
setuptools    44.0.0 
{% endhighlight %}

If we install a new library, it will install to the virtual environment's **site-packages**, not system wide. 
Installing **numpy** with pip will add it to **~/venvs/searing-frost/lib/python3.8/site-packages/numpy**.

{% highlight bash %}
(searing-frost)~/venvs/searing-frost$ pip install numpy
(searing-frost)~/venvs/searing-frost$ pip list

Package       Version
------------- -------
numpy         1.19.1 
pip           20.0.2 
pkg-resources 0.0.0  
setuptools    44.0.0 
{% endhighlight %}

A requirements.txt file for the project related to the virtual environment can be created easily with **pip freeze**.
Package the requirements.txt with the project source code so everyone can install the same version of libraries. 
Check out my blog post on [pip](% post_url 2020-07-31-python-library-tenacity%}) for more details.

{% highlight bash %}
(searing-frost)~/venvs/searing-frost$ pip freeze > ~/searing-frost-project/requirements.txt

requirements.txt
----------------
numpy==1.19.1
{% endhighlight %}

