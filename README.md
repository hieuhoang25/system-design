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
## 4. Proxy, ForwardProxy and Reverse Proxy
- Proxy: Một proxy (proxy server) là một máy chủ trung gian giữa người dùng và các nguồn tài nguyên mạng (ví dụ: máy chủ web hoặc dịch vụ trực tuyến). Khi người dùng gửi yêu cầu đến proxy, proxy sẽ chuyển tiếp yêu cầu đó đến nguồn tài nguyên tương ứng và trả về kết quả cho người dùng. Điều này giúp che giấu địa chỉ IP thực sự của người dùng và cung cấp các lợi ích khác như bảo mật, tăng tốc độ truy cập và kiểm soát truy cập vào nguồn tài nguyên.
- Reverse Proxy: Một reverse proxy (reverse proxy server) cũng là một máy chủ trung gian, nhưng nó chuyển tiếp yêu cầu từ người dùng đến các máy chủ back-end hoặc các nguồn tài nguyên khác. Khi người dùng gửi yêu cầu đến reverse proxy, reverse proxy sẽ định tuyến yêu cầu đến máy chủ back-end tương ứng và trả về kết quả cho người dùng. Điều này giúp tăng cường hiệu suất, phân tải tải và cân bằng tải cho hệ thống server. Ngoài ra, reverse proxy cũng có thể cung cấp các tính năng bảo mật như bảo vệ chống tấn công DDoS và bảo vệ ẩn danh.
- Forward proxy :

* Ẩn danh và bảo mật: Forward proxy giúp che giấu địa chỉ IP thực sự của người dùng khi gửi yêu cầu đến các máy chủ hoặc dịch vụ. Điều này cung cấp một lớp ẩn danh và bảo mật cho người dùng.

* Kiểm soát truy cập: Forward proxy cho phép người quản trị mạng kiểm soát truy cập vào các nguồn tài nguyên trên Internet. Bằng cách cấu hình forward proxy, các quy tắc và chính sách truy cập có thể được áp dụng để kiểm soát và giới hạn quyền truy cập từ các người dùng.

* Tăng tốc truy cập: Forward proxy có thể lưu lại bộ nhớ cache của các yêu cầu trước đó từ người dùng. Khi có yêu cầu tương tự, forward proxy có thể trả về kết quả từ cache mà không cần gửi yêu cầu đến máy chủ hoặc dịch vụ, giúp tăng tốc độ truy cập.

* Bộ lọc và bảo vệ: Forward proxy có thể được cấu hình để áp dụng các bộ lọc và quy tắc bảo vệ, như chặn truy cập vào các trang web độc hại, quảng cáo, hoặc nội dung không phù hợp.
## 5. Cách sử dụng file cấu hình application-dev.yml và application-aws.yml trong quá trình triển khai có thể phụ thuộc vào quy trình triển khai và cách bạn cấu hình ứng dụng.

- Sử dụng trực tiếp: Một số framework và thư viện cho phép bạn sử dụng các file cấu hình này trực tiếp trong quá trình triển khai. Khi triển khai ứng dụng, bạn chỉ cần đảm bảo rằng các file application-dev.yml và application-aws.yml được đưa vào vị trí cấu hình chính xác và ứng dụng sẽ tự động đọc và áp dụng các cấu hình từ các file này.

- Sử dụng thủ công: Trong một số trường hợp, bạn có thể cần sử dụng các công cụ hoặc kịch bản tùy chỉnh để xử lý các file cấu hình này. Ví dụ, bạn có thể sử dụng kịch bản triển khai (deployment script) để sao chép và đặt các file cấu hình vào vị trí cần thiết trên máy chủ triển khai. Sau đó, bạn có thể khởi động lại ứng dụng hoặc thực hiện các bước tiếp theo để áp dụng các cấu hình từ các file này.

- Cách sử dụng trực tiếp hay thủ công phụ thuộc vào quy trình triển khai và các công cụ mà bạn đang sử dụng. Đối với các nền tảng và công cụ triển khai như Docker, Kubernetes, Ansible, hoặc các nền tảng điện toán đám mây, bạn có thể sử dụng các kịch bản triển khai hoặc công cụ quản lý cấu hình để tự động sao chép và áp dụng các file cấu hình này.
### 6. Certificate Concept in security system
In the context of security systems, the concept of certificates revolves around the use of digital certificates to establish trust, authenticate entities, and ensure secure communication. Here's an overview of the certificate concept in security systems:
- Digital Certificates: In security systems, digital certificates are electronic documents that verify the identity of a particular entity, such as a person, device, or organization. They contain information about the entity, including its public key, and are issued and signed by a trusted certification authority (CA).
- Public Key Infrastructure (PKI): Digital certificates are a fundamental component of a PKI, which is a system that manages the creation, distribution, and revocation of certificates. PKI provides a framework for secure communication, encryption, and authentication in various security systems.
- Authentication and Trust: Certificates play a crucial role in verifying the authenticity and trustworthiness of entities involved in security systems. By digitally signing certificates, CAs vouch for the identity of the entity and confirm that the public key associated with the certificate belongs to the claimed entity.
- Secure Communication: Certificates are commonly used in secure communication protocols such as Transport Layer Security (TLS) and Secure Sockets Layer (SSL). In these protocols, certificates are used to authenticate the server's identity to the client and establish an encrypted and secure communication channel.
- Certificate Authorities (CAs): CAs are trusted entities responsible for issuing and managing digital certificates. They follow strict procedures to verify the identity of entities before issuing certificates. Popular CAs include public CAs like Let's Encrypt and private CAs within organizations.
- Certificate Chains and Trust Hierarchies: Certificates can form a chain of trust, where a root CA signs intermediate CAs, and intermediate CAs sign end-entity certificates. This hierarchical structure allows for the delegation of trust and enables verification of certificates by relying parties.
- Revocation and Expiration: Certificates have an expiration date after which they are no longer considered valid. Additionally, certificates can be revoked before expiration if the private key is compromised or if the entity no longer meets the trust criteria. Certificate revocation mechanisms, such as Certificate Revocation Lists (CRLs) and Online Certificate Status Protocol (OCSP), are used to manage revocations.
***Certificates in security systems provide a means to verify and establish trust in the digital realm. They are essential for securing communication channels, authenticating entities, and protecting sensitive information. By leveraging digital certificates, security systems can ensure confidentiality, integrity, and authenticity in various domains, including network security, web applications, e-commerce, and identity management.***
### 7.  HTTP-Only Cookie
An HTTP-only cookie is a type of cookie that is set with the HTTP-only flag. This flag is an additional attribute that can be included when a cookie is sent from the server to the client (usually through an HTTP response). When the HTTP-only flag is present, it instructs the client's web browser to restrict access to the cookie, preventing it from being accessed or modified by JavaScript code running on the client-side.

The purpose of using HTTP-only cookies is to enhance the security of web applications. By restricting access to cookies, it helps mitigate certain types of attacks, such as cross-site scripting (XSS) attacks. XSS attacks involve injecting malicious scripts into a website, which can be used to steal sensitive information, including cookies. However, since JavaScript code cannot access HTTP-only cookies, it significantly reduces the risk of such attacks.

HTTP-only cookies can only be accessed and sent back to the server by the client's web browser during subsequent HTTP requests. They are typically used for session management, storing user authentication tokens, and other sensitive information that should not be accessible to client-side scripts.

To set an HTTP-only cookie in an HTTP response, the server includes the HttpOnly attribute in the Set-Cookie header. Here's an example:
`Set-Cookie: sessionid=abcd1234; Path=/; HttpOnly`

In this example, the sessionid cookie is marked as HTTP-only with the HttpOnly attribute. The browser will honor this attribute and ensure that the cookie is only accessible through the HTTP protocol.

It's important to note that although HTTP-only cookies enhance security, they are not a complete solution for preventing all types of attacks. Other security measures, such as secure transmission of data over HTTPS, input validation, and proper server-side security practices, should also be implemented to ensure the overall security of a web application.
### Cơ chế hoạt động của HTTP Only cookie trong việc làm mới (refresh) token trong ứng dụng web có thể được mô tả như sau:

- Đầu tiên, khi người dùng đăng nhập vào ứng dụng và gửi yêu cầu xác thực, máy chủ sẽ tạo một cặp cookie bao gồm một cookie session và một cookie refresh token. Cookie session thường có thời gian sống ngắn hơn, trong khi cookie refresh token sẽ có thời gian sống lâu hơn.

- Cookie session được thiết lập với thuộc tính HTTP Only, điều này có nghĩa là nó chỉ có thể được truy cập thông qua giao thức HTTP và không thể truy cập bằng JavaScript. Điều này giúp ngăn chặn tấn công Cross-Site Scripting (XSS), trong đó kẻ tấn công có thể đánh cắp cookie thông qua mã JavaScript độc hại.

- Khi access token hết hạn, người dùng tiếp tục sử dụng ứng dụng và gửi yêu cầu xác thực, máy chủ sẽ kiểm tra xem cookie session có tồn tại hay không. Nếu cookie session vẫn còn hiệu lực, máy chủ sẽ tạo lại access token mới và gửi nó đến client thông qua phản hồi HTTP.

- Nếu cookie session đã hết hạn hoặc không tồn tại, máy chủ sẽ kiểm tra cookie refresh token. Nếu cookie refresh token còn hiệu lực, máy chủ sẽ sử dụng nó để tạo lại cặp cookie session và access token mới, và gửi chúng đến client.

- Nếu cả cookie session và cookie refresh token đều đã hết hạn hoặc không tồn tại, người dùng sẽ bị đăng xuất khỏi ứng dụng và được yêu cầu đăng nhập lại.

- Tóm lại, cơ chế hoạt động của HTTP Only cookie trong việc làm mới token (refresh token) giúp bảo vệ thông tin xác thực của người dùng bằng cách giới hạn truy cập của cookie chỉ thông qua giao thức HTTP và ngăn chặn tấn công XSS. Nó cho phép máy chủ sử dụng cookie refresh token để tạo lại session và access token khi cần thiết, giúp duy trì phiên làm việc của người dùng trong ứng dụng web.
