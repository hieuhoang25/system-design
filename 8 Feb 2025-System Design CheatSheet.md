# System Design CheatSheet for Interview
![alt text](image-56.png)
![alt text](image-57.png)
![alt text](image-58.png)![alt text](image-59.png)
## Rest API
![alt text](image-60.png)
![alt text](image-61.png)![alt text](image-62.png)
![alt text](image-63.png)![alt text](image-64.png)
![alt text](image-65.png)![alt text](image-66.png)
![alt text](image-67.png)![alt text](image-68.png)
![alt text](image-69.png)![alt text](image-70.png)
![alt text](image-71.png)![alt text](image-72.png)
![alt text](image-73.png)![alt text](image-74.png)
## Network
![alt text](image-75.png)![alt text](image-76.png)
## Server
![alt text](image-77.png)
## AWS Networking cheatsheet
![alt text](image-78.png)
## OAuth & JWT
![alt text](image-79.png)![alt text](image-80.png)
![alt text](image-81.png)
## Session vs Cookies
![alt text](image-82.png)
![alt text](image-83.png)
Cookies and sessions are both used to carry user information over HTTP requests, including user login status, user permissions, etc.
1. Cookies
Cookies typically have size limits (4KB). They carry small pieces of information and are stored on the users’ devices. Cookies are sent with each subsequent user request. Users can choose to ban cookies in their browsers.
2. Sessions
Unlike cookies, sessions are created and stored on the server side. There is usually a unique session ID generated on the server, which is attached to a specific user session. This session ID is returned to the client side in a cookie. Sessions can hold larger amounts of data. Since the session data is not directly accessed by the client, the session offers more security.
![alt text](image-84.png)
## CI/CD WorkFlow
![alt text](image-85.png)![alt text](image-86.png)
## Kafka Internal working & Usecase
![alt text](image-87.png)![alt text](image-88.png)
## Database
![alt text](image-89.png)![alt text](image-90.png)
![alt text](image-91.png)
![alt text](image-92.png)![alt text](image-93.png)
![alt text](image-94.png)![alt text](image-95.png)
![alt text](image-96.png)![alt text](image-97.png)
## Software Architecture
![alt text](image-98.png)![alt text](image-99.png)
## System design Acronyms
![alt text](image-100.png)
## Data Pipeline Overview
![alt text](image-101.png)
## System Testing
![alt text](image-102.png)
## Git Working
![alt text](image-103.png)![alt text](image-104.png)
To begin with, it’s essential to identify where our code is stored. The common assumption is that there are only two locations — one on a remote server like Github and the other on our local machine. However, this isn’t entirely accurate. Git maintains three local storages on our machine, which means that our code can be found in four places:
<br>
- Working directory: where we edit files
- Staging area: a temporary location where files are kept for the next commit
- Local repository: contains the code that has been committed
- Remote repository: the remote server that stores the code

![alt text](image-105.png)
![alt text](image-106.png)
## Code Review and Ship to Production
![alt text](image-107.png)
![alt text](image-108.png)
## Docker , Kubernetes
![alt text](image-109.png)
![alt text](image-110.png)
![alt text](image-111.png)
![alt text](image-112.png)
![alt text](image-113.png)
![alt text](image-114.png)
![alt text](image-115.png)
In a traditional software development, code, build, test, release and monitoring are siloed functions. Each stage works independently and hands over to the next stage.

DevOps, on the other hand, encourages continuous development and collaboration between developers and operations. This shortens the overall life cycle and provides continuous software delivery.

NoOps is a newer concept with the development of serverless computing. Since we can architect the system using FaaS (Function-as-a-Service) and BaaS (Backend-as-a-Service), the cloud service providers can take care of most operations tasks. The developers can focus on feature development and automate operations tasks.

NoOps is a pragmatic and effective methodology for startups or smaller-scale applications, which moves shortens the SDLC even more than DevOps.

## Https Working
![alt text](image-116.png)
## API Gateway
![alt text](image-117.png)
## Microservices
![alt text](image-118.png)![alt text](image-119.png)
![alt text](image-120.png)
## URL vs URI vs URN
![alt text](image-121.png)
![alt text](image-122.png)
## Design Patterns
![alt text](image-123.png)
## Logging and Tracing
![alt text](image-124.png)
## Routing policies
![alt text](image-125.png)
## Load Balancing
![alt text](image-126.png)
Static Algorithms

Round robin
The client requests are sent to different service instances in sequential order. The services are usually required to be stateless.
Sticky round-robin
This is an improvement of the round-robin algorithm. If Alice’s first request goes to service A, the following requests go to service A as well.
Weighted round-robin
The admin can specify the weight for each service. The ones with a higher weight handle more requests than others.

Hash
This algorithm applies a hash function on the incoming requests’ IP or URL. The requests are routed to relevant instances based on the hash function result.

Dynamic Algorithms

Least connections
A new request is sent to the service instance with the least concurrent connections.
Least response time
A new request is sent to the service instance with the fastest response time.
## Encryption
![alt text](image-127.png)
## Message Queue
![alt text](image-128.png) ![alt text](image-129.png)
![alt text](image-130.png)
## Object Storage
![alt text](image-131.png)
## API vs SDK
![alt text](image-132.png)
## Forward vs Reverse Proxy
![alt text](image-133.png)
## Caching
![alt text](image-134.png) ![alt text](image-135.png)
## Cloud Native
![alt text](image-136.png) ![alt text](image-137.png)
![alt text](image-138.png)
## Event Sourcing
![alt text](image-139.png)
## Firewall
![alt text](image-140.png)
## Distributed system
![alt text](image-141.png)
## Batch vs Stream Processing
![alt text](image-142.png)
## CDN — Content Delivery Network
![alt text](image-143.png)

