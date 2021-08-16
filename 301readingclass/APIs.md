# APIs

## What does REST stand for?

Representational state transfer (REST): is a software architectural style that was created to guide the design and development of the architecture for the World Wide Web. REST defines a set of constraints for how the architecture of an Internet-scale distributed hypermedia system, such as the Web, should behave. The REST architectural style emphasises the scalability of interactions between components, uniform interfaces, independent deployment of components, and the creation of a layered architecture to facilitate caching components to reduce user-perceived latency, enforce security, and encapsulate legacy systems. REST has been employed throughout the software industry and is a widely accepted set of guidelines for creating stateless, reliable web services.

Any web service that obeys the REST constraints is informally described as RESTful. Such a web service must provide its Web resources in a textual representation and allow them to be read and modified with a stateless protocol and a predefined set of operations. This approach allows the greatest interoperability between clients and servers in a long-lived Internet-scale environment which crosses organisational (trust) boundaries.


## REST APIs are designed around !

REST or RESTful API design (Representational State Transfer) is designed to take advantage of existing protocols. While REST can be used over nearly any protocol, it usually takes advantage of HTTP when used for Web APIs. This means that developers do not need to install libraries or additional software in order to take advantage of a REST API design. It is notable for its incredible layer of flexibility. Since data is not tied to methods and resources, REST has the ability to handle multiple types of calls, return different data formats and even change structurally with the correct implementation of hypermedia.

This freedom and flexibility inherent in REST API design allow you to build an API that meets your needs while also meeting the needs of very diverse customers. Unlike SOAP, REST is not constrained to XML, but instead can return XML, JSON, YAML or any other format depending on what the client requests. And unlike RPC, users aren’t required to know procedure names or specific parameters in a specific order.



## What is an identifer of a resource? Give an example.

These URIs provide a good example of the interaction between a URI and a URL. For modeling purposes, any URI in one of these namespaces (e.g., http://www.w3.org ..

Syntax of Uniform Resource Identifiers (URIs) — The Web requires one of these two, but browsers also ... www.example.com is the domain name or authority ...

## What are the most common HTTP verbs?

The primary or most-commonly-used HTTP verbs (or methods, as they are properly called) are POST, GET, PUT, PATCH, and DELETE. These correspond to create, read, update, and delete (or CRUD) operations, respectively.


## What should the URIs be based on?


A Uniform Resource Identifier (URI) is a unique sequence of characters that identifies a logical or physical resource used by web technologies.
The purpose of URIs is to uniquely and reliably name resources on the Web. According to Cool URIs for the Semantic Web (W3C IG Note), URIs should be designed with simplicity, stability and manageability in mind, thinking about them as identifiers rather than as names for Web resources.

## Give an example of a good URI.!

1) example.com/articles/3252
 2) example.com/articles/how+to+design+good+uri
3) example.com/articles/3252/how+to+design+good+uri
4) example.com/good-uri-design
5) example.com/articles/good-uri-design
6) example.com/a/good-uri-design

---
## What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?


In URLs, nouns are good; verbs are bad
A consequence of REST’s data-oriented model is that every URL identifies a thing. This means that—for
well-known URLs and query URLs that are designed to be read and written by programmers of API
clients—the URLs should be formed from nouns, which are the natural language part of speech used to
designate things.

## What status code does a successful GET request return?


Generally, this means that the server provided the requested page. ... This means the server successfully processed the request, but is not returning any content. Unlike a 204 response, this response requires that the requester reset the document view.


## What status code does an unsuccessful GET request return?


If not valid, 400 Bad Request is returned. Order is processed. If the order is successful, a 201 Created is returned for the order. If an unexpected error is encountered, a 500 Server Error is returned.

## What status code does a successful POST request return?


This means the request was successful and the server created a new resource. ... This means the server successfully processed the request, but is not returning any content. Unlike a 204 response, this response requires that the requester reset the document view.

## What status code does a successful DELETE request return?
 

 A successful response of DELETE requests SHOULD be HTTP response code 200 (OK) if the response includes an entity describing the status, 202 (Accepted) if the action has been queued, or 204 (No Content) if the action has been performed but the response does not include an entity.



## How would you match your name using RegEx?

Here.
~~~
^[a-zA-Z'-]+$
~~~

- ^ means start of the string, and $ means end of the string.
- […] is a character class which anything inside it will be matched.
- x+ means the pattern before it can be repeated once or more.
Inside the character class,

- a-z and A-Z are the lower and upper case alphabets,
- ' is the apostrophe, and
- is the hyphen. The hyphen must appear at the beginning or the end to avoid confusion with the range separator as in a-z.

**Note that** this class won't match international characters e.g. ä. You have to include them separately e.g.
~~~
^[-'a-zA-ZÀ-ÖØ-öø-ſ]+$
~~~