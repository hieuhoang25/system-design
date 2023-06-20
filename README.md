# System Design
## 1. Tomcat and Netty
1. Netty:
***Netty is an asynchronous event-driven network application framework. It provides a high-performance, low-level networking API that enables the development of various network protocols and applications. Netty focuses on building scalable, high-performance network servers and clients.***

- Key features of Netty include:

- - Non-blocking I/O: Netty uses an event-driven model with non-blocking I/O operations, allowing for efficient handling of multiple connections without requiring a large number of threads.
- - High throughput: Netty is optimized for high throughput and low latency, making it suitable for applications that require high-performance networking.
- - Protocol support: Netty provides built-in support for various network protocols and allows for custom protocol implementations.
- - Flexibility: Netty offers a flexible and extensible API, making it possible to customize and extend the framework as per application requirements.
2. Tomcat:
***Tomcat, officially known as Apache Tomcat, is a widely used web server and servlet container. It provides an environment for running Java web applications, including support for Java servlets, JavaServer Pages (JSP), and WebSocket applications.***

- Key features of Tomcat include:

- - Servlet container: Tomcat implements the Java Servlet and JavaServer Pages specifications, allowing developers to deploy and run web applications written in Java.
Web server capabilities: Tomcat can act as a standalone web server, serving static files and handling HTTP requests.
- - Java EE compatibility: Tomcat supports Java Enterprise Edition (Java EE) specifications and can be used as a lightweight alternative to full-fledged Java EE application servers like JBoss or WebLogic.
- - Management and monitoring: Tomcat provides various tools and interfaces for managing and monitoring deployed applications, including a web-based administration console.
***In summary, Netty is primarily focused on low-level network programming and building high-performance network applications, while Tomcat is designed for running Java web applications and serving HTTP requests. Depending on your specific use case, you would choose one over the other.***
https://github.com/angular-vietnam/100-days-of-angular
