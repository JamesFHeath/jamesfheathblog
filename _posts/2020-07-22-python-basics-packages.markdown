---
layout: post
title:  "Python Basics: Packages"
categories: python programming
tags: python packages import 
---

### Packages Introduction
Python *packages* are just a folder containing Python modules. 
Python packages just require an __init__.py file, often blank, inside of them to be recognized as a package. 
You can think of packages as a level up of organization from modules. 
Packages can even contain subpackages. 

### Importing Packages
To import packages, you use the import keyword to import the definitions in the package's \_\_init\_\_.py or modules inside the package. 
Dot notation is used to get to subpackages and definitions within modules. 
<br>
my_package/
<br>
|
<br>
|\_\_\_ \_\_init\_\_.py
<br>
|\_\_\_ my\_module.py
<br>
|\_\_\_\_\_\_my_subpackage_1/
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ \_\_init\_\_.py
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ my_submodule_1.py
<br>
|\_\_\_\_\_\_my_subpackage_2/
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ \_\_init\_\_.py
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ my_submodule_1.py
<br>

{% highlight python %}
# Imports definitions my_package's from __init__.py
import my_package

# Imports the definitions in my_module
import my_package.my_module

# Imports definitions from my_subpackage_1's __init__.py
import my_package.my_subpackage_1

# Imports my_module into the namespace
from my_package import my_module

# Imports my_submodule_1 into the namespace
from my_package.my_subpackage_1 import my_submodule_1
{% endhighlight %}

### Creating your own Packages
Following the Python documentation on [creating packages](https://packaging.python.org/tutorials/packaging-projects/), we need to create a few files. 
The most important is setup.py, as it defines the metadata for our package. 
It includes things like author name, other libraries needed to install, and the package version. 
The sample package is [linked here](https://github.com/JamesFHeath/jamesfheathblog_code/tree/master/Python%20Basics/Sample%20Package).

{% highlight python %}
# setup.py
import setuptools

setuptools.setup(
    name="PythonBasicsPackages",
    version="1.0.0",
    author="Me",
    author_email="jamesheathradford@gmail.com",
    description="Python Basics Package",
    long_description="A sample package to demonstrate how pip installs user packages",
    long_description_content_type="text/markdown",
    url="https://github.com/JamesFHeath/jamesfheathblog_code/tree/master/Python%20Basics",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.6',
)

{% endhighlight %}

<br>
Sample Package/
<br>
|
<br>
|\_\_\_ setup.py
<br>
|\_\_\_\_\_\_PythonBasicsPackages/
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ \_\_init\_\_.py
<br>
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|\_\_\_ sample_module.py
<br>

You simply install it by running pip install on the setup.py directory.

{% highlight bash %}
pip install /path/to/Sample Package/
{% endhighlight %}

Then you just import like any other package. 

{% highlight python %}
from PythonBasicsPackage import sample_module
{% endhighlight %}