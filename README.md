# What is API

API is Application Programming Interface

* It is set of subroutine definitions, protocols and tools for building application software. 
* It helps in connecting various software components.
* An API makes it easier for developers to use certain technologies in building applications by using predefined operations. 

# Purpose of API

* One purpose of APIs is to hide the internal details of how a system works, exposing only those parts a programmer will find useful and keeping them consistent even if the internal details later change. 
* An API may be custom-built for a particular pair of systems, or it may be a shared standard allowing interoperability among many systems.

# Remote API

Remote APIs allow developers to manipulate remote resources through protocols, specific standards for communication that allow different technologies to work together, regardless of language or platform. For example, the Java Database Connectivity API allows developers to query many different types of databases with the same set of functions, while the Java remote method invocation API uses the Java Remote Method Protocol to allow invocation of functions that operate remotely, but appear local to the developer.

# REST Framework 

* It describes an architecture which stands for REpresentational State Transfer
* It is used for web based architecture for data communication
* It uses HTTP to make calls between machines

Common used HTTP methods : 

* GET  - To retreive a resource
* PUT - To modify resource
* POST - To send resource
* DELETE - To delete the resource

# What is a REST API ? 

* When Web services use REST architecture, they are called RESTful APIs or REST APIs.
* It is a set of web addresses that respond with pure information, not a formatted web page.
* An API returns a JSON, which is a common format. {},[]

# Install REST API

* Requirements are python and pip 
* On terminal type 
```
pip install djangorestframework
```

# Add to Django Project

* Add `rest_framework` to your INSTALLED_APPS setting.
```
INSTALLED_APPs = (
...
'rest_framework',
)
```
