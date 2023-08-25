# Reading Notes Class #32

<ol>

><li> What makes an API RESTful?

An API (Application Programming Interface) is considered RESTful (Representational State Transfer) when it adheres to the principles and constraints defined by the REST architectural style. REST is a set of guidelines for designing networked applications, particularly web services, in a way that is scalable, flexible, and efficient. Here are the key characteristics that make an API RESTful:

1. **Client-Server Architecture**: A RESTful API separates the client (consumer of the API) and the server (provider of the API). This separation allows for independent development and scalability of both components.

2. **Stateless Interaction**: Each request from a client to the server must contain all the necessary information to process the request. The server should not rely on any context or session stored on the server itself.

3. **Cacheability**: Responses from the server can be marked as cacheable or non-cacheable. Caching improves performance by allowing clients to reuse previously obtained responses, reducing the need to make redundant requests.

4. **Uniform Interface**: This is a fundamental principle of REST and includes several sub-constraints:
   - **Resource Identification**: Resources (entities) are identified using a unique URI (Uniform Resource Identifier).
   - **Resource Manipulation through Representations**: Resources are represented using standard formats such as JSON or XML. Clients interact with resources by sending and receiving representations.
   - **Self-Descriptive Messages**: Each message contains all the information needed for the recipient to understand how to process it. This reduces coupling between client and server.
   - **Hypermedia as the Engine of Application State (HATEOAS)**: The server includes hyperlinks in responses to guide clients to related resources. This enables clients to navigate the API without prior knowledge.

5. **Layered System**: The architecture can be composed of multiple layers, with each layer having a specific function. This separation allows for modularity and easier scalability.

6. **Code on Demand (Optional)**: This constraint is optional and not commonly used. It allows the server to send executable code to the client, extending the client's capabilities.

7. **Client-Cache-Server Interaction**: The client can cache responses to reduce the number of requests made to the server. The server can include cache control directives in its responses.

8. **State Transfer**: Communication between the client and server is done through the transfer of representations of resources. Clients request changes to the resource state by sending representations to the server.

In summary, a RESTful API follows a set of principles that promote simplicity, scalability, and separation of concerns. It uses standard HTTP methods (GET, POST, PUT, DELETE) and adheres to the concepts of resources, representations, and hypermedia to enable efficient communication between clients and servers.

</li>

<ol>

[HOME](../README.md)
