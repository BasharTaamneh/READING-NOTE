# REST


## Who is Roy Fielding?
Roy T. Fielding, Senior Principal Scientist at Adobe, is known for his pioneering work on the World Wide Web, open source, and software architecture. He wrote the standards for HTTP/1. x and URI, has been a contributor to many other Web technologies, and defined the REST architectural style.

## Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?

Because they weren't designed to be used like that. When Fielding and his colleagues started building the web, being able to talk to any machine anywhere in the world was a primary concern. But most of the techniques developers later used to get computers to talk to each other didn't have those requirements. You just needed to talk to a small group of machines.

##  What is the HTTP protocol that Fielding and his friends created?


The Hypertext Transfer Protocol (HTTP) is an application-level protocol for distributed, collaborative, hypermedia information systems.


## What does a GET do?

GET is used to request data from a specified resource.

GET is one of the most common HTTP methods.

Note that the query string (name/value pairs) is sent in the URL of a GET request:
~~~
/test/demo_form.php?name1=value1&name2=value2
~~~
**Some other notes on GET requests:**

. GET requests can be cached

. GET requests remain in the browser history

. GET requests can be bookmarked

. GET requests should never be used when dealing with sensitive data

. GET requests have length restrictions

. GET requests are only used to request data (not modify)

## What does a POST do?
POST is used to send data to a server to create/update a resource.

The data sent to the server with POST is stored in the request body of the HTTP request:
~~~
POST /test/demo_form.php HTTP/1.1
Host: w3schools.com
name1=value1&name2=value2
~~~
**POST is one of the most common HTTP methods.**

*Some other notes on POST requests:*

. POST requests are never cached

. POST requests do not remain in the browser history

. POST requests cannot be bookmarked

. POST requests have no restrictions on data length

## What does PUT do?


PUT method is used to update resource available on the server. Typically, it replaces whatever exists at the target URL with something else. You can use it to make a new resource or overwrite an existing one.

## What does PATCH do?


A patch is a set of changes to a computer program or its supporting data designed to update, fix, or improve it. This includes fixing security vulnerabilities and other bugs, with such patches usually being called bugfixes or bug fixes.

