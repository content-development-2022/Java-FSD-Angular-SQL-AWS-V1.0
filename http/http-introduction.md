What is HTTP

-   HTTP stands for Hypertext Transfer Protocol.
-   Hypertext Transfer Protocol is a set of rule which is used for transferring the files like, audio, video, graphic image, text and other multimedia files on the WWW (World Wide Web).
-   HTTP is an application-level protocol. The communication usually takes place through TCP/IP sockets, but any reliable transport can also be used.
-   The standard (default) port for HTTP connection is 80, but other port can also be used.
-   The first version of HTTP was HTTP/0.9, which was introduced in 1991.
-   The latest version of HTTP is HTTP/3, which was published in September 2019. It is an alternative to its processor HTTP/2.
-   This latest version is already in use on the web with the help of UDP (User Datagram Protocol) instead of TCP (Transmission Control Protocol) for the underlying transport protocol.
-   HTTP is used to make communication between a variety of hosts and clients. It supports a mixture of network configuration.
-   HTTP is a protocol that is used to transfer the hypertext from the client end to the server end, but HTTP does not have any security.
-   Whenever a user opens their Web Browser, that means the user indirectly uses HTTP.

## Three important things about HTTP

**Connectionless:** HTTP is connectionless. When the HTTP client opens the browser, the browser initiates an HTTP request. After making the request, the client disconnect from the server and wait for the response. When the response is ready, the server re-establish the connection again and delivers the response to the client, after which the client disconnects the connection. So both client and server know about each other during the current request and response only.

**Media Independent:** HTTP is media independent. HTTP can deliver any sort of data, as long as the two computers can read it.

**Stateless:** The HTTP is stateless. The client and server just know about each other just during the current request. If the connection is closed, and two computers want to connect again, they need to provide information to each other anew, and the connection is handled as the very first one.

HTTP Needs

-   The HTTP was designed mainly to fetch the html document and send it to the client. That all the HTTP was doing in 1991, and it did not support other media types, it just delivers html document.
-   It was designed in an exquisite way, and it was continually evolved, and features were being added to it, it becomes the most convenient way to quickly and reliably move data on the web.

What is HTTPS

-   HTTPS stands for Hypertext Transfer Protocol Secure. HTTPS has a secure transfer.
-   It was developed by Netscape.
-   HTTPS is used to encrypt or decrypt user HTTP page or HTTP page requests that are returned by the webserver.
-   HTTPS is first used in HTTP/1.1 and is defined in RFC 2616.
-   In HTTPS, the standard port to transfer the information is 443.
-   Using the HTTPS, sensitive information that we want to transfer from one user to another user can be done securely.
-   HTTPS protocol uses HTTP on connection encrypted by SSL (Secure Socket Layer) or TLS (Transport Layer Security).
-   HTTPS protects transmitted data from man-in-the-middle (MITM) attacks and eavesdropping.
-   It is the default protocol for conduction financial transactions on the web.
