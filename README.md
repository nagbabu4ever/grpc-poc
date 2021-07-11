# What Is gRPC?
gRPC is a high performance, open-source universal RPC framework. By default it uses Protocol Buffers to define exposed services.

### GRPC
gRPC is a modern open source high performance RPC framework that can run in any environment. It can efficiently connect services in and across data centers with pluggable support for load balancing, tracing, health checking and authentication. It is also applicable in last mile of distributed computing to connect devices, mobile applications and browsers to backend services. more @ https://grpc.io/


![alt text](https://github.com/nagbabu4ever/grpc-poc/blob/main/grpc.jpg)

## What is Protobuf
Protocol buffers, usually referred as Protobuf, is a protocol developed by Google to allow serialization and deserialization of structured data. Google developed it with the goal to provide a better way, compared to XML, to make systems communicate. So they focused on making it simpler, smaller, faster and more maintainable then XML. But, as you will see in this article, this protocol even surpassed JSON with better performance, better maintainability and smaller size.

### How Does it Differs from JSON?
It is important to note that, although JSON and Protobuf messages can be used interchangeably, these technologies were designed with different goals. JSON, which stands for JavaScript Object Notation, is simply a message format that arose from a subset of the JavaScript programming language. JSON messages are exchanged in text format and, nowadays, they are completely independent and supported by, virtually, all programming languages.

Protobuf, on the other hand, is more than a message format, it is also a set of rules and tools to define and exchange these messages. Google, the creator of this protocol, has made it open source and provides tools to generate code for the most used programming languages around, like JavaScript, Java, PHP, C#, Ruby, Objective C, Python, C++ and Go. Besides that, Protobuf has more data types than JSON, like enumerates and methods, and is also heavily used on RPCs (Remote Procedure Calls).

### Is Protobuf Really Faster than JSON?
There are several resources online that show that Protobuf performs better than JSON, XML and etc - like this one and this one -, but it is always important to check if this is the case for your own needs and use case. Here, at Auth0, I have developed a simple Spring Boot application to test a few scenarios and measure how JSON and Protobuf performed. Mostly I have tested serialization of both protocols to make two Java applications communicate and to make a JavaScript web application communicate to this backend.

The main reason to create these two scenarios - Java to Java and JavaScript to Java - was to measure how this protocol would behave in an enterprise environment like Java and also on an environment where JSON is the native message format. That is, what I show here is data from an environment where JSON is built in and should perform extremely fast (JavaScript engines) and from an environment where JSON is not a first class citizen.

gRPC vs REST
---------------------
Where REST is more flexible about encoding, gRPC standardizes on Protobuf.
Where REST can be either schemaless or use a 3rd-party schema, gRPC always declares the service and messages in a Protobuf schema definition.

gRPC vs SOAP
---------------------
Where SOAP is more flexible about transport, gRPC standardizes on HTTP/2.
Where in SOAP protocols are often set in stone once defined (often requiring a new path for every version of the service), Protobuf is explicitly intended to support schema evolution.
