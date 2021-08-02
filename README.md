# What is API

API is Application Programming Interface

* It is set of subroutine definitions, protocols and tools for building application software. 
* It helps in connecting various software components.
* An API makes it easier for developers to use certain technologies in building applications by using predefined operations. 

# Purpose of API

* One purpose of APIs is to hide the internal details of how a system works, exposing only those parts a programmer will find useful and keeping them consistent even if the internal details later change. 
* An API may be custom-built for a particular pair of systems, or it may be a shared standard allowing interoperability among many systems.

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
