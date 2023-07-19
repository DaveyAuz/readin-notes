# Reading Notes Class #9

<ol>

><li> What are the five steps in the HTTP Request Lifecycle?

The HTTP (Hypertext Transfer Protocol) request lifecycle involves a series of steps that occur when a client (such as a web browser) sends a request to a web server to retrieve a resource. The following are the five steps in the HTTP request lifecycle:

* DNS Resolution: The client needs to resolve the domain name (e.g., <www.example.com>) to an IP address. This process is called DNS resolution. The client sends a request to the Domain Name System (DNS) server, which returns the corresponding IP address for the domain.

* TCP Connection: After obtaining the IP address, the client establishes a TCP (Transmission Control Protocol) connection with the server. TCP ensures reliable data transmission by creating a connection-oriented communication channel between the client and the server.

* HTTP Request: Once the TCP connection is established, the client sends an HTTP request to the server. The request consists of several components, including the HTTP method (e.g., GET, POST, PUT, DELETE), the path to the requested resource, HTTP headers (e.g., User-Agent, Host), and optionally a message body (used for methods like POST).

* 0Server Processing: Upon receiving the HTTP request, the server processes it based on the information provided in the request. The server may perform various tasks, such as routing the request to the appropriate handler, processing the data in the message body (if applicable), authenticating the client, and determining the requested resource.

* HTTP Response: After processing the request, the server generates an HTTP response. The response contains an HTTP status code indicating the success or failure of the request (e.g., 200 OK, 404 Not Found, 500 Internal Server Error), HTTP headers with additional information (e.g., Content-Type, Content-Length), and optionally a message body containing the requested resource or any other data.

Once the HTTP response is ready, the server sends it back to the client through the established TCP connection. The client then processes the response to display the requested resource or handle any errors encountered during the request-response cycle.

</li>

><li> What are the two things the client needs before it can make an HTTP Request?

Before a client can make an HTTP request to a web server, it needs two essential pieces of information:

* URL (Uniform Resource Locator): The URL is a string that specifies the address of the resource the client wants to access. It typically consists of the protocol (e.g., "http://" or "https://"), the domain name (e.g., "www.example.com"), and the path to the specific resource on the server (e.g., "/page.html"). In some cases, URLs may also contain query parameters to pass additional information to the server (e.g., "?id=123").

* DNS Resolution: The client needs to resolve the domain name from the URL to its corresponding IP address. This process is called DNS resolution. The client sends a request to a Domain Name System (DNS) server, which returns the IP address associated with the domain name. The IP address is required to establish a TCP connection with the server and send the HTTP request.

With both the URL and the IP address obtained through DNS resolution, the client can then proceed to make the HTTP request to the server, specifying the resource it wants to retrieve and any other relevant information, such as HTTP headers or message body data (for certain request methods like POST or PUT)

</li>

><li> Explain the four way handshake and what it does.

The "four-way handshake" is a process used to establish and terminate a secure connection between a client and a server using Transport Layer Security (TLS) or Secure Sockets Layer (SSL) protocols. TLS and SSL are cryptographic protocols that provide secure communication over a computer network, commonly used to secure data transmission over the internet, such as in HTTPS connections.

The four-way handshake involves a series of steps between the client (usually a web browser) and the server to negotiate the encryption parameters and establish a secure connection. Likewise, during connection termination, the four-way handshake is used to gracefully close the secure connection.

Here are the four steps involved in the handshake:

 1) Client Hello: The client initiates the handshake by sending a "Client Hello" message to the server. This message contains information about the TLS/SSL versions supported by the client, a random value (known as the "Client Random"), and a list of supported cipher suites (encryption algorithms). The server will choose one of the cipher suites from the list to use for encryption.

 2) Server Hello: Upon receiving the "Client Hello" message, the server responds with a "Server Hello" message. In this message, the server selects the highest TLS/SSL version that is supported by both the client and the server. It generates its own random value (the "Server Random") and chooses a cipher suite from the client's list. The server also sends its digital certificate, which includes its public key.

 3) Client Key Exchange and Certificate Verification: After the "Server Hello," the client verifies the server's digital certificate to ensure it is valid and issued by a trusted certificate authority. If the certificate is valid, the client generates a pre-master secret and encrypts it using the server's public key (from the certificate). The client then sends this encrypted pre-master secret back to the server, ensuring that only the server can decrypt it using its private key.

 4) Server Key Exchange and Session Establishment: Once the server receives the encrypted pre-master secret from the client, it decrypts it using its private key to obtain the pre-master secret. Both the client and the server independently derive the master secret from the pre-master secret and their respective random values (Client Random and Server Random). This master secret is used to generate encryption keys and other security parameters for the session. The secure connection is now established, and both the client and the server can begin encrypted data transmission.

When it comes to connection termination, the four-way handshake is also used to close the connection:

1) Client Sends Close Notify: The client sends a "Close Notify" alert to the server, indicating that it intends to terminate the connection.

2) Server Acknowledges Close Notify: The server responds with its own "Close Notify" alert, acknowledging the client's request to close the connection.

3) Server Sends Close Notify: The server then sends its "Close Notify" alert to the client, indicating that it also intends to terminate the connection.

4) Client Acknowledges Close Notify: Finally, the client acknowledges the server's "Close Notify" alert, completing the termination process. The connection is now closed.

The four-way handshake ensures a secure and authenticated connection between the client and the server, protecting data transmitted over the network from unauthorized access and tampering.

</li>

><li> True or False: When making an HTTP request, you MUST follow any redirect returned by the request. Back up your answer.

True, when making an HTTP request, you MUST follow any redirect returned by the request.

The HTTP protocol includes status codes to provide information about the outcome of a request. When a client sends an HTTP request to a server, the server may respond with a status code indicating the result of the request. One of the status codes used for redirects is the "3xx" series. When a server returns a 3xx status code, it is instructing the client to redirect the request to a different URL.

The most common redirect status codes are:

* 301 Moved Permanently: The requested resource has been permanently moved to a new URL. The client should update its records and use the new URL for future requests.

* 302 Found (or 303 See Other): The requested resource temporarily resides under a different URL. The client should follow the redirect but continue to use the original URL for future requests.

* 307 Temporary Redirect: Similar to 302, the requested resource temporarily resides under a different URL. The client should follow the redirect and repeat the request using the original method.

* 308 Permanent Redirect: Similar to 301, the requested resource has been permanently moved to a new URL. The client should follow the redirect and use the new URL for future requests.

The reason you should follow redirects is to ensure that the client can access the correct resource. If a client encounters a redirect status code and does not follow it, it might end up accessing outdated or non-existent resources. By automatically following redirects, the client can reach the intended destination of the request, whether the resource has been moved permanently or temporarily.

Most web browsers and HTTP client libraries automatically handle redirects, so developers don't need to handle them explicitly. This behavior ensures that users can access websites and resources even when URLs change or when multiple servers or load balancers are involved.

</li>

><li> Which built-in Java class can be used to perform an HTTP request?

In Java, you can use the java.net.HttpURLConnection class to perform an HTTP request. HttpURLConnection is a built-in class provided by the Java Standard Library (Java SE) that allows you to establish a connection to a URL and interact with web servers using the HTTP protocol.

Here's a basic example of how you can use HttpURLConnection to make an HTTP GET request:

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class HttpGetExample {
    public static void main(String[] args) {
        try {
            // URL to make the HTTP GET request to
            URL url = new URL("https://api.example.com/data");

            // Open a connection to the URL
            HttpURLConnection conn = (HttpURLConnection) url.openConnection();

            // Set the request method (GET)
            conn.setRequestMethod("GET");

            // Read the response from the server
            BufferedReader reader = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            StringBuilder response = new StringBuilder();
            String line;
            while ((line = reader.readLine()) != null) {
                response.append(line);
            }
            reader.close();

            // Print the response
            System.out.println("Response: " + response.toString());

            // Disconnect the connection
            conn.disconnect();

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

```

Please note that this is a basic example for making an HTTP GET request. For more complex use cases or when dealing with sensitive data, it's recommended to use more robust HTTP client libraries like Apache HttpClient or Java's java.net.HttpClient (introduced in Java 11), which provide additional features and better performance.

</li>

><li> What HTTP status codes represent a successful response? A redirect? A client error?

HTTP status codes are three-digit numbers returned by a web server in response to an HTTP request made by a client (such as a web browser or an API client). These status codes provide information about the outcome of the request. Here are the categories of HTTP status codes and some examples for each category:

1) Successful Responses (2xx):

* 200 OK: The request was successful, and the server has returned the requested data.
* 201 Created: The request was successful, and a new resource was created as a result.
* 204 No Content: The request was successful, but there is no additional information to send in the response (often used for DELETE requests).

2) Redirects (3xx):

* 301 Moved Permanently: The requested resource has been permanently moved to a new URL.
* 302 Found (or 303 See Other): The requested resource temporarily resides under a different URL.
* 307 Temporary Redirect: Similar to 302, the requested resource temporarily resides under a different URL.

3) Client Errors (4xx):

* 400 Bad Request: The server could not understand the request due to a client error or malformed request syntax.
* 401 Unauthorized: The client must authenticate itself to get the requested response (usually via HTTP Basic or Digest Authentication).
* 404 Not Found: The requested resource could not be found on the server.

It's worth mentioning that the HTTP status codes are grouped into five classes, each represented by the first digit of the status code:

* 1xx: Informational responses (e.g., 100 Continue, 101 Switching Protocols).
* 2xx: Successful responses as mentioned above.
* 3xx: Redirection responses as mentioned above.
* 4xx: Client error responses as mentioned above.
* 5xx: Server error responses (e.g., 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable).

These status codes are an essential part of the HTTP protocol and provide valuable information about the success or failure of a request, helping both clients and servers handle requests appropriately.



</li>

</ol>

[HOME](../README.md)
