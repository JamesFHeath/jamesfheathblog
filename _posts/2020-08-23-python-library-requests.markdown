---
layout: post
title:  "Python Library: Requests"
categories: python programming
tags: python requests http
---

### Requests
[Requests](https://requests.readthedocs.io/en/master/) is a fantastic open-source library for sending HTTP requests. 
Requests abstracts away the details and complications of the standard libary [urllib module](https://docs.python.org/3/library/urllib.request.html#module-urllib.request).
Requests can be installed with **pip install requests**.

| HTTP Method | requests |
|:------|:--------|
| GET | requests.get(url, params=None, **kwargs) |
| POST | requests.post(url, data=None, json=None, **kwargs) |
| OPTIONS | requests.options(url, **kwargs) |
| HEAD | requests.head(url, **kwargs) |
| PUT | requests.put(url, data=None, **kwargs) |
| DELETE | requests.delete(url, **kwargs) |
| PATCH | requests.patch(url, data=None, **kwargs) |

### Simple Get Request
To see how easy using requests is, let's just make a get request for the James Heath Blog. 

{% highlight python %}
import requests

blog_url = 'https://blog.jamesfheath.com'
# Response object contains all you need
response = requests.get(blog_url)

print(response.status_code)
# 200

# String of the HTML
print(response.text)
# '<!DOCTYPE html>\n<html lang="en">\n\n<link re...'

# Prints out the raw HTML bytes
print(response.content)
# b'<!DOCTYPE html>\n<html lang="en">\n\n<link re...'
{% endhighlight %}

### National Weather Service API
Requests is great for communicating with APIs. 
Let's try out some requests with query parameters and headers. 
The [National Weather Service](https://www.weather.gov/documentation/services-web-api) has an open API that we can use to test requests out. 

{% highlight python %}
import requests

weather_url = 'https://api.weather.gov'
# We will ask for a list of weather stations
stations_url = f'{weather_url}/stations'

# Header to give our identity
headers = {'User-Agent': '(jamesfheath.com, jamesheathradford@gmail.com)'}

# Asking for 10 stations from North Carolina or Virginia
params = {'state': ['NC', 'VA'],
          'limit': 10}

response = requests.get(url=station_url, headers=headers, params=params)

# JSON response as a Python dict
print(response.json())
# {'@context': ['https://geojson.org/geojson-ld/geojson-context.jsonld',
#  {'@version': '1.1',}
# ...

# Use Python syntax to operate on the dict
print(response.json()['features'][1]['properties']['name'])
# 'KG4EUF Virginia Beach'

# String response
print(response.text)
# '{\n    "@context": [\n        "https://geojson.org/geojson-ld/geojson-context.jsonld",\n 
{% endhighlight %}

Anything you need to specify will be passed into the HTTP method you choose. 
Some common examples are **timeout** and **authorization**. 
Mostly, requests just works exactly how you hope it would, and it makes your life dealing with HTTP simple. 