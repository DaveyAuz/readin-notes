# Reading-Notes Class 6
<Ol>

><li> Who is Roy Fielding?
Roy Fielding is a computer scientist and one of the principal authors of the HTTP protocol, which is the foundation of data communication for the World Wide Web. He is also known for his contributions to the development of several other web-related technologies and standards, including URI (Uniform Resource Identifier), REST (Representational State Transfer), and SSL (Secure Sockets Layer).

Fielding received his Ph.D. in Information and Computer Science from the University of California, Irvine, where he worked on the design of the HTTP protocol with his advisor, Dr. Richard N. Taylor. His doctoral dissertation, titled "Architectural Styles and the Design of Network-based Software Architectures," introduced the REST architectural style, which has become a widely adopted approach to designing web-based applications and services.

In addition to his work on web technologies, Fielding has also been a vocal advocate for open standards and open source software. He is currently a Senior Principal Scientist at Adobe Systems and continues to be actively involved in the development of web standards and protocols.

</li>

><li>Why don’t the techniques that we use in this class work well when we need to be able to talk to all of the machines in the world?

The techniques used in our Code Fellows Classes focus on connecting a limited number of machines within a controlled environment, such as a local area network (LAN) or a wide area network (WAN) that is owned and managed by a single organization. These techniques are generally designed to optimize performance, security, and reliability within the boundaries of the network.

However, when we need to communicate with all of the machines in the world, such as in the case of the Internet, the challenges are much more complex. The Internet is a global network of networks, and it is decentralized and open, with no single entity controlling all of the machines or the data that flows between them.

To communicate effectively over the Internet, we need to use techniques and protocols that are designed to handle the scale, complexity, and heterogeneity of the network. For example, we need to use a protocol such as the Transmission Control Protocol/Internet Protocol (TCP/IP) that can handle the routing of packets of data across different networks and over long distances. We also need to use addressing schemes such as the Domain Name System (DNS) to map human-readable domain names to IP addresses that can be used by routers to deliver packets to their destination.

In addition to these technical challenges, we also need to consider issues such as security, privacy, and governance when communicating over the Internet. These issues are often not covered in a typical computer networking class and require a broader understanding of the social, economic, and political dimensions of the Internet.

</li>

><li>What is the HTTP protocol that Fielding and his friends created?

The Hypertext Transfer Protocol (HTTP) is a protocol that governs the communication between web servers and clients, such as web browsers. HTTP was first developed by Tim Berners-Lee and his team at CERN in the early 1990s as a way to exchange data and documents on the World Wide Web.

Roy Fielding, one of the principal authors of the HTTP protocol, contributed significantly to the development of HTTP 1.1, which is the most widely used version of the protocol today. The HTTP protocol is based on a client-server architecture, in which the client (typically a web browser) sends a request to the server for a resource, and the server responds with the requested data.

HTTP uses a simple, text-based format to exchange messages between the client and server. Each message consists of a request or response line, a set of headers that provide additional information about the message, and an optional message body that contains the data being exchanged.

Over the years, HTTP has evolved to support additional features and functionality, including support for secure connections (HTTPS), caching, and authentication. The latest version of the protocol, HTTP/3, was standardized in 2020 and is designed to improve performance over high-latency networks by using the QUIC transport protocol.

</li>

><li>What does a GET do?

In the context of the HTTP protocol, a GET request is used by a client (such as a web browser) to request a representation of a specific resource from a web server. The resource can be a web page, an image, a video, or any other type of data that is accessible over the web.

When a client sends a GET request to a server, the request message includes the URL (Uniform Resource Locator) of the resource being requested, along with any optional query parameters that are used to modify the request. The server responds to the request with an HTTP response message that contains the requested data and additional metadata, such as the HTTP status code and headers.

It's important to note that a GET request is a "safe" and "idempotent" operation, which means that it should not have any side effects on the server or the resource being requested, and it can be repeated multiple times without changing the state of the server or the resource. In other words, a GET request should only retrieve data from the server and should not modify or update any data on the server.


><li> What does a POST do?
In the context of the HTTP protocol, a POST request is used by a client (such as a web browser) to submit data to a web server to create or update a resource. The resource can be a web page, a form submission, or any other type of data that is accessible over the web.

When a client sends a POST request to a server, the request message includes the URL (Uniform Resource Locator) of the resource being created or updated, along with the data being submitted in the request body. The data can be in various formats such as JSON, XML, or plain text.

The server then processes the request and responds with an HTTP response message that contains the HTTP status code and optional response data.

It's important to note that a POST request is considered a "non-idempotent" operation, which means that if the request is repeated, it may result in the creation of multiple resources or duplicate data on the server. Therefore, a POST request should only be used when it is intended to create or update a resource on the server, and not for retrieving data from the server.

In contrast, a GET request is used to retrieve data from the server, and it is considered a "safe" and "idempotent" operation, which means that it should not have any side effects on the server or the resource being requested, and it can be repeated multiple times without changing the state of the server or the resource.
</li>

><li> What does PUT do?
In the context of the HTTP protocol, a PUT request is used by a client (such as a web browser) to update or replace an existing resource on a web server. The resource can be a web page, an image, a file, or any other type of data that is accessible over the web.

When a client sends a PUT request to a server, the request message includes the URL (Uniform Resource Locator) of the resource being updated, along with the new data that is being submitted in the request body. The server then processes the request and updates the existing resource with the new data.

It's important to note that a PUT request is considered an "idempotent" operation, which means that if the request is repeated, it should not have any additional side effects on the server or the resource being updated. In other words, sending the same PUT request multiple times should result in the same final state on the server.

If the resource being updated does not exist on the server, the server may choose to create a new resource instead of returning an error, depending on the server implementation and configuration.

In contrast, a POST request is typically used to create a new resource on the server, and it is considered a "non-idempotent" operation, which means that if the request is repeated, it may result in the creation of multiple resources or duplicate data on the server.
</li>

><li> What does PATCH do?
In the context of the HTTP protocol, a PATCH request is used by a client (such as a web browser) to partially modify an existing resource on a web server. The resource can be a web page, an image, a file, or any other type of data that is accessible over the web.

When a client sends a PATCH request to a server, the request message includes the URL (Uniform Resource Locator) of the resource being updated, along with a set of instructions on how to modify the resource in the request body. These instructions are typically expressed in a format such as JSON Patch or JSON Merge Patch.

The server then processes the request and applies the specified modifications to the existing resource, updating only the affected parts of the resource while leaving the rest of the resource unchanged.

It's important to note that a PATCH request is considered a "partially idempotent" operation, which means that if the request is repeated, it should not have any additional side effects on the server or the resource being updated, but it may result in a different final state on the server. In other words, sending the same PATCH request multiple times should result in the same final state for the modified parts of the resource, but the unmodified parts of the resource may change if other changes are made to those parts.

If the resource being updated does not exist on the server, the server may choose to create a new resource instead of returning an error, depending on the server implementation and configuration.

In contrast, a PUT request is typically used to completely replace an existing resource on the server, while a POST request is typically used to create a new resource on the server.
</li>

</ol>
[HOME](../README.md)