# API

An API is Application Programming Interface that defines a set of rules which allow programs to talk to each other.

## REST API:

REST stands for representational state transfer. It's an architectural guideline that defines a set of rules that must be followed while creating an API so that the API can be called RESTful.

REST uses HTTP to have clients request resources from a server via a URL. An HTTP request will have following parts

1. A Method (Verb) to define the nature of the request
2. An endpoint which specifies the resource that needs to be accessed.
3. Headers
4. Body

Following guidelines need to be following in order for an API to be Restful:

1. Have client server architecture.

2. Have a layered system that organizes each type of server catering to client's request (Security, LB, App Server, DB etc)

3. Uniform interfacte between components. This entails that each requested resource should have self contained info for the client to process it in a desired manner.

4. Cacheable: The client should be allowed to cache the response from a request in order to streamline the client server interaction.

5. Code on Demand

6. Stateless: Server shouldn't be allowed to store the state between two requests.


`It has to be remembered that REST is an architectural guideline, and not a protocol`

A REST API can return data in a variety of formats (HTML, XML, plain text, JSON)


## SOAP API:

SOAP stands for Simple Object Access protocol. Like REST it defines how APIs should be built. `However, unlike REST it's a specific protocol and imposes built in rules`.

These rules may lead to increases complexity and overhead, which can cause increased page load times. But this also means that there's a stricter enforcement of standards which causes it to be chosen for enterprise level software. Standards built into SOAP include Security, ACID etc.

SOAP often uses WSDL which is a web service specification (Web Services Description Language).

SOAP API requests can be handled through any application layer protocol like HTTP, SMTP, or Transport layer protocol like TCP. The response are always in XML format and are not cacheable like REST.
