# SOAP vs REST vs GraphQL

## SOAP 
- Simple Object Access Protocol
- Introduced in 1998
- Basically a protocol
- Operates with the two basic functions – GET and POST. GET is used to retrieve data from the server, while POST is used to add or modify data.
- Performs operations representing logic
- SOAP, with XML used as data format, is far too verbose, both on the request and the response side, thus requiring more resources and slowing down the communication.
- Supports single data format, XML.
- Data is defined on the server side.
- Has no inherent caching and requires additional mechanisms on the client side.
- Communication protocols - HTTP, TCP, SMTP.
- Supports single endpoint.
- Versioning available.

## REST
- Representational State Transfer
- Introduced in 2000
- Basically an architectural style
- Changes the state of the corresponding source by making a request to the URI (Uniform Resource Identifier).
- Operate with resources representing data.
- REST, since its structure is more plain and obvious, with its endpoint requests seemed to be a silver bullet, thus has rapidly turned into the protocol of choice among open API architecture developers.
- Can process XML, HTML, and JSON.
- Data is defined on the server side.
- The server defines which data is to be returned.
- Uses the HTTP caching mechanism.
- Communication protocols - HTTP only.
- Supports multiple endpoints.
- Versioning available.


## GraphQL
- New data query language by Facebook
- Introduced in 2015
- It is a query language.
- Leverages requests of two types – queries retrieving data from the server, and mutations changing the data.
- Operate with resources representing data.
- Much more lightweight with respect to network payload.
- Can process only JSON.
- The data definition functions are on the client side.
- The server only declares the available data, and the client specifies what should be returned.
- Has no inherent caching and requires additional mechanisms on the client side, such as Apollo Client.
- Communication protocols - HTTP only.
- Supports single endpoint.
- Versioning not available.


