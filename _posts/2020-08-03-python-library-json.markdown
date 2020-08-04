---
layout: post
title:  "Python Library: JSON"
categories: python programming
tags: python json
---

# JSON
[JSON is JavaScript Object Notation](https://www.json.org/json-en.html) and it is a data interchange format used widely on the web and elsewhere. 
The nature of JavaScript is dynamic, and Python works well for parsing and working with JSON. 
The standard library of Python has a wonderful JSON module that makes working with JSON simple. 

# JSON to Python
JSON maps nicely to Python objects when parsed. When translating Python to JSON, this process is reversible. However, more complex Python objects like datetime or namedtuples will not translate without custom behavior specified. 

| JSON | Python |
|:------|:--------|
| String | String |
| Number | Int or Float |
| Object | Dictionary |
| Array | List |
| null | None |
| true | True |
| false | False |

# Loads and Dumps
The main operations used with the JSON library are **loads** and **dumps**. 
**loads** takes in a String of JSON and parses it into the corresponding Python objects. 
**dumps** is the reverse, it takes a Python object and creates a String of JSON. 
You'll often receive JSON responses from web servers and parse them with **loads**. 
Then you can create a Python object and stringify it with **dumps** to send back.  

{% highlight python %}
import json

# I like using single quotes, especially for JSON strings
# because then you don't need to escape double quotes
json_string = '{"key": "value", "array_key": [1, 2, 3], "another_key_for_boolean": false}'

python_object = json.loads(json_string)
print(python_object)
# {'key': 'value', 'array_key': [1, 2, 3], 'another_key_for_boolean': False}
{% endhighlight %}

Now we can operate on the Python object with our normal Python syntax. 
Once we are done, we can create a new JSON string. 

{% highlight python %}
python_object['new_key'] = None
python_object['array_key'].append(4)

new_json_string = json.dumps(python_object)

print(new_json_string)
# '{"key": "value", "array_key": [1, 2, 3, 4], "another_key_for_boolean": false, "new_key": null}'
{% endhighlight %}

Another other nice features of **dumps** is the ability to pretty print with the *indent* parameter. 
Just specify a number for the indentation, and the JSON string will be nicely formatted for human readable output. 

{% highlight python %}
import json

python_object = {'parent': {'child_1': [1, 2, 3], 'child_2': True}}

json.dumps(python_object, indent=4)

{% endhighlight %}

{% highlight javascript %}
{
    "parent": {
        "child_1": [
            1,
            2,
            3
        ],
        "child_2": true
    }
}

{% endhighlight %}

# Overriding default dumps behavior
Some objects are not directly translatable into JSON. 
**datetime** objects are a great example and will come up often. 

{% highlight python %}
import datetime

now = datetime.datetime.now()
# datetime.datetime(2020, 8, 3, 20, 35, 38, 299215)

json.dumps(now)
# TypeError: Object of type datetime is not JSON serializable
{% endhighlight %}

The solution to creating JSON strings with **datetime** and other complex objects is to subclass the **JSONEncoder** class and implement a **default** method that returns a Python object that *can* be encoded. 
For a **datetime** object, turn it into a dictionary with a key of 'datetime_now' and a string representation of the datetime object, which *is* JSON serializable. 

{% highlight python %}
import datetime
import json

now = datetime.datetime.now()

class DateTimeEncoder(json.JSONEncoder):
    def default(self, o):
        if type(o) == datetime.datetime:
            return {'datetime_now': str(o)}
        return json.JSONEncoder.default(self, o)

date_time_encoder = DateTimeEncoder()

now_json_string = date_time_encoder.encode(now)

print(now_json_string)
# '{"datetime_now": "2020-08-03 20:35:38.299215"}'
{% endhighlight %}