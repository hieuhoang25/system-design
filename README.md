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
- - Recapchar architectures
## 2. Nginx in production
***Frontend không cần nginx để deploy, nhưng việc sử dụng Nginx có nhiều lợi ích khi triển khai ứng dụng frontend trong môi trường sản phẩm. Dưới đây là một số lý do phổ biến:***
- Web Server: Nginx có thể hoạt động như một web server để phục vụ các tệp tĩnh (HTML, CSS, JavaScript) cho trình duyệt của người dùng. Điều này giúp tối ưu hóa việc phục vụ tệp tĩnh và cải thiện hiệu suất của ứng dụng.

- Cân bằng tải (Load Balancing): Nếu bạn triển khai nhiều phiên bản của ứng dụng frontend trên các máy chủ khác nhau, Nginx có thể được cấu hình để cân bằng tải trên các máy chủ này. Điều này giúp phân phối công việc đồng đều và tăng khả năng chịu tải của hệ thống.

- Bộ đệm (Caching): Nginx có khả năng lưu trữ tạm thời (cache) các tệp tĩnh, giúp giảm tải cho máy chủ ứng dụng và cung cấp thời gian phản hồi nhanh hơn cho người dùng. Bộ đệm này giúp giảm tải cho backend và cải thiện hiệu suất tổng thể.

- Gzip Compression: Nginx hỗ trợ nén Gzip, giúp giảm kích thước các tệp tin trước khi gửi đến trình duyệt. Điều này giúp tăng tốc độ tải trang và giảm lưu lượng mạng cần thiết để truyền dữ liệu.

- SSL/TLS Offloading: Nginx có thể được cấu hình để xử lý SSL/TLS, giải phóng máy chủ ứng dụng khỏi việc xử lý mã hóa và giải mã truyền thông bảo mật. Điều này giúp giảm tải cho backend và cải thiện hiệu suất.

- Proxy Server: Nginx có khả năng hoạt động như một proxy server, giúp chuyển tiếp yêu cầu từ trình duyệt đến backend của ứng dụng. Điều này cho phép thực hiện các tác vụ như định tuyến yêu cầu, chuyển tiếp HTTP hoặc HTTPS, ẩn danh và nhiều hơn nữa.
## 3. JCanary
- Java library for canary checks on web services.

- Canary checks are similar to a health check, with the main difference being that it tests the system much deeper. Health checks usually collect a number of indicators and for each of those the result is either UP or DOWN. If the service is unhealthy, a health endpoint usually returns a non-200 status code. This has important impacts on load balancers and orchestration systems like Kubernetes.

- A canary endpoint reveals much more sophisticate information and can be used for general monitoring of service, as opposed to just detecting if it's functioning or not functioning.

- For example, your service might depend on a third party for some API calls, but not all of them. In such case, the canary endpoint might return information about that third party being down. Your service might also depend on a scheduled task running every X hours. The canary endpoint could raise an alarm if no task was run in the last X+1 hours.
- https://github.com/MartinBechtle/jcanary
