---
layout: post
title:  "Python Library: XML with LXML"
categories: python programming
tags: python xml lxml
---

# Introduction to XML and LXML
[XML](https://www.w3schools.com/xml/) stands for eXtensible Markup Language, and it's a base for defining other markup languages.
[HTML](https://www.w3schools.com/html/) is the most well known XML, being the basis for all webpages. 
Python has a standard library, called [**xml**](https://docs.python.org/3/library/xml.html), for working with XML files. 
It does the job, but today we'll be talking about the [**lxml**](https://lxml.de/) library, which is more feature rich.
**lxmls**'s biggest advantages are is its full ipmlementation of [XPath](https://www.w3schools.com/XML/xml_xpath.asp) and it's factory functions for creating XML elements. 

# Element Tree
The goal of **lxml** is to work with XML using the [ElementTree API](https://lxml.de/api/index.html).
Every XML tag is an element, each element contains a name and potentially attributes, child elements, and text. 
Element tree attributes work like Python dictionaries, and child elements are in a Python list. 
This allows for standard Python syntax to work seamlessly with **etree** elements. 

# Parsing XML to Elements
**lxml** can read from files or string objects of XML and parse them into **etree** elements. 

{% highlight xml %}
 <?xml version="1.0" encoding="UTF-8"?>
 <store>
    <inventory>
        <apples count="5">Golden Delicious</apples>
        <oranges count="0"/>
    </inventory>
    <employees>
        <employee title="writer">SearingFrost</employee>
    </employees>
 </store>
{% endhighlight %}

{% highlight python %}
xml_string = '<?xml version="1.0" encoding="UTF-8"?><store><inventory>...</store>'

store = etree.fromstring(xml_string)
# root is the root element, in this case store
{% endhighlight %}

# Serializing/Writing Elements to XML
XML travels in string format, so the ability to transform **lxml** elements into strings is vital. 
Luckily, it is very simple with the **tostring** function. 
**tostring** just reverses the **fromstring** function. 

{% highlight python %}
print(etree.tostring(store, encoding='utf-8', xml_declaration=True, pretty_print=True))
# b'<?xml version=\'1.0\' encoding=\'utf-8\'?><store><inventory>...</store>'
{% endhighlight %}

# Searching and Modifying XML objects 

The most effective way to search for XML Elements is with [XPath](https://www.w3schools.com/xml/xpath_intro.asp).
XPath is fully implemented in **lxml**, 
{% highlight python %}
{% endhighlight %}

Searching can also be accomplished using iterators to go through elements until you find what you need. 
[**iterwalk**](https://lxml.de/api/lxml.etree.iterwalk-class.html) is a class and part of etree that will take an Element and iterate through the Element's tree. 
**iterwalk**'s iterator returns tuples of events and elements.
When elements are encountered, they can be mutated as needed. 

{% highlight python %}
# Iterating through the store
# returning start and end events
# We can see SearingFrost is changed to NewName inplace
for event, element in etree.iterwalk(store, events=('start', 'end')):
    print(event, element)
    if element.tag == 'SearingFrost':
        element.tag = 'NewName'
# start <Element store at 0x107240700>
# start <Element inventory at 0x1081d0540>
# start <Element apples at 0x1081d6580>
# end <Element apples at 0x1081d6580>
# start <Element oranges at 0x1081d6600>
# end <Element oranges at 0x1081d6600>
# end <Element inventory at 0x1081d0540>
# start <Element employees at 0x1081c0b00>
# start <Element SearingFrost at 0x1081d05c0>
# end <Element NewName at 0x1081d05c0>
# end <Element employees at 0x1081c0b00>
# end <Element store at 0x107240700>
{% endhighlight %}

# Creating XML objects 
**lxml** also makes it possible to build your own XML trees from scratch. 
After you start with a root [element](http://effbot.org/zone/pythondoc-elementtree-ElementTree.htm#elementtree.ElementTree.ElementTree-class) the XML tree is built mostly with calls to **etree.subelement**. 
The [subelement factory](http://effbot.org/zone/pythondoc-elementtree-ElementTree.htm#elementtree.ElementTree.SubElement-function) takes a parent, tag name, an optional attribute dictionary, and extra keyword arguments if necessary. Let's recreate the store XML document using subelements. 
{% highlight python %}
from lxml import etree

store = etree.Element('store')
inventory = etree.SubElement(store, 'inventory')
# Be mindful when adding assigning variables after
# the .text on SubElement call, as it will return 
# the text and not the Element
etree.SubElement(inventory, 'apples', {'count': '5'}).text = 'Golden Delicious'
etree.SubElement(inventory, 'oranges', {'count': '0'})
employees = etree.SubElement(store, 'employees')
etree.SubElement(employees, 'SearingFrost', {'title': 'writer'})

print(etree.tostring(store, encoding='utf-8', xml_declaration=True, pretty_print=True))
# b'<?xml version=\'1.0\' encoding=\'utf-8\'?><store><inventory>...</store>'
{% endhighlight %}



# Namespaces
Finally, we're going to dig into namespaces with a fair amount of detail. 
[Namespaces](https://www.w3.org/TR/REC-xml-names/#sec-namespaces) are an important part of XML, and **lxml** provides full utility to work with them. 
Namespaces are prefixes for tag names to avoid tag names clashing.
Namespaces use [URI's](https://www.rfc-editor.org/rfc/rfc3986.txt), which are essentially more generic URL's, in that URI's do not need to describe how to locate a resource. 
Namespaces are defined in the root attributes of XML elements that use that namespace (often the root element of an XML document will contain all the namespaces used).
Declarations use a special attribute name **xmlns:**namespace="URI/of/namespace".
Remember, the URI doesn't necessarily have to point to anything real, it just needs to be unique so it doesn't clash with other namespaces. 
{% highlight xml %}
<root xmlns:searing="https://www.jamesfheath.com/xmlnamespaces" xmlns:frost="https://www.jamesfheath.com/xmlnamespaces">
    <searing:store>store with the searing namespace</searing:store>
    <frost:store>store with the frost namespace</frost:store>
</root>
{% endhighlight %}

**lxml** uses *fully qualified* namespaces and not just *prefixes* in order to avoid ambiguity and make code easier to write. 
When the final XML document is seraialized, it simply translates back into the prefix as expected.  

| lxml QName | Prefix |
|:-----|:-----|
| {https://www.jamesfheath.com/xmlnamespaces}searing | searing |

{% highlight python %}
{% endhighlight %}