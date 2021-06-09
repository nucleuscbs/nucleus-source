---
layout: post
title: Decoding APIs?
description: Let’s decode one of the fanciest terminology in data science, the API.
date: 2020-09-08
featured: no
---


What is an API?

Application Program Interface. Wait you didn’t ask for its expansion, you wanted to know what an API actually meant and what it is used for; but sadly, this what you get to know once you google for an API and then you get extremely confused. As always, we’re here to help.


An API, enables developers to integrate one app with another. They are the interfaces provided by servers that you can use to, among others, retrieve and send data using code. 

A simpler explanation?

Let’s assume you wanted to ask Github to send you all the user details for your study. Even though you wanted the data for the study, Github cannot give you login credentials (email, password, etc.) of other users in your hands. But Github can do one thing, it can provide you with a portal/interface from where you could fetch limited user data (like only no. of commits made, no. of repositories, etc.). This interface is called an API. An API enables developers (like you ;)) to integrate one app (your python code) with another (like Github). They are the interfaces provided by servers that you can use to, among others, retrieve and send data using code. 

Why use APIs?

APIs can help you fetch real-time data for your application in a well-structured way. They help in automating things that might have taken months if you did them manually using your web browser.

How do APIs send data?

Most of the APIs send data in JSON (JavaScript Object Notation). JSON is a lightweight format for storing and transporting data. It looks like a python dictionary or a python array. Hence, all the manipulation you did on python dictionaries and arrays come in handy here. It looks like:
{% highlight python %}
{
	“name”:”the analytics bay”,
	“Organization”:”Nuclues”,
	“helpful”:”true”
}
{% endhighlight %}
Status Codes

Before we deep dive into using APIs, we need to know how the server will respond to our requests. When a request fails, we can have different reasons for the same; maybe the server wasn’t functioning properly or we requested for something strange. All of this information is communicated using HTTP status codes, which are 3-digit numbers divided into categories.

Informational responses (100–199),

Successful responses (200–299), =>This is what we aim for

Redirects (300–399),

Client errors (400–499) => The errors from client side (due to us) 

and Server errors (500–599) => The errors from server side

What is a request?

You would encounter three major terminologies that sum up to make a request:

Endpoints => This is usually a url from which you need to fetch data

Methods => either GET, PUT, POST, or DELETE. 

Headers => this contains information regarding authentication.

When are we going to actually work with APIs?

Now, Let’s fetch data from covid19api.com. First, we need to find the right endpoint. You can do so by looking up the API documentation of the same https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#7934d316-f751-4914-9909-39f1901caeb8

We would be using an inbuilt library json (to convert json response to python object) and install the requests library (to use its methods to make requests for data)
{% highlight python %}
pip install requests		//installing requests
import json		//importing json library
import requests		//importing requests
api_base_url= ‘https://api.covid19api.com/dayone/country/india /status/confirmed’	//endpoint
api_key	=’SOME KEY’	//use this only if you need to make request from a protected API
headers = {'Content-Type': 'application/json',
       //'Authorization': 'Bearer {0}'.format(api_key) add this line if the endpoint is protected
}
response = requests.get(api_base_url, headers=headers)		//using get method of requests
json_response = json.loads(response.content.decode('utf-8'))		//using json.loads to convert json data to python
{% endhighlight %}
Let’s Print json_response to see what we got
print(json_response)

Output:
{% highlight json %}
[{'Cases': 1,
  'City': '',
  'CityCode': '',
  'Country': 'India',
  'CountryCode': 'IN',
  'Date': '2020-01-30T00:00:00Z',
  'Lat': '20.59',
  'Lon': '78.96',
  'Province': '',
  'Status': 'confirmed'},
 {'Cases': 1,
  'City': '',
  'CityCode': '',
  'Country': 'India',
  'CountryCode': 'IN',
  'Date': '2020-01-31T00:00:00Z',
  'Lat': '20.59',
  'Lon': '78.96',
  'Province': '',
  'Status': 'confirmed'},
.
.
.
{'Cases': 456183,
  'City': '',
  'CityCode': '',
  'Country': 'India',
  'CountryCode': 'IN',
  'Date': '2020-06-23T00:00:00Z',
  'Lat': '20.59',
  'Lon': '78.96',
  'Province': '',
  'Status': 'confirmed'},
 {'Cases': 473105,
  'City': '',
  'CityCode': '',
  'Country': 'India',
  'CountryCode': 'IN',
  'Date': '2020-06-24T00:00:00Z',
  'Lat': '20.59',
  'Lon': '78.96',
  'Province': '',
  'Status': 'confirmed'}]

{% endhighlight %}

You can see we received an array of dictionaries. Now we need to iterate between the array to access data (keys and values) inside dictionary.
{% highlight python %}
Dates = []
Cases=[]
for item in json_response:
  Cases.append(item['Cases'])
  Dates.append(item['Date'])
{% endhighlight %}

Let’s plot the Dates with the no. of cases.
{% highlight python %}
import matplotlib.pyplot as plt

plt.figure(figsize=(20,12.5))
plt.plot(Dates,Cases)
plt.xlabel('Date')
plt.ylabel('Close')
plt.grid(axis='y', color='0.95')
plt.show()
{% endhighlight %}
  
<img src="/blog/api.jpg">


And we told you! API’s did it. They can do much more wonders when used the right way for the right projects. You can even create one (but that’s a blog for another day). Hope you have a good understanding of the use case of this beautiful piece of technology in data science.
