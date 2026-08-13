Sure 👍 Below is a **GitHub-ready `notes.md` file**. You can copy everything inside the block and paste it directly into your `Day-31-Cloud-Load-Balancing/notes.md`.

# Day 31 – Cloud Load Balancing

## 1. Introduction

Cloud Load Balancing is a technique used to distribute incoming network traffic across multiple servers, virtual machines, containers, or application instances.

Instead of sending all requests to a single server, a load balancer distributes the requests among multiple healthy backend resources.

### Basic Architecture

```text
                Users
                  |
                  v
            Load Balancer
             /     |     \
            v      v      v
        Server 1 Server 2 Server 3
```

This helps applications achieve better performance, scalability, reliability, and availability.

---

## 2. Why Load Balancing is Required

When an application becomes popular, a single server may receive a large number of requests.

This can result in:

* High CPU and memory usage
* Slow response times
* Server overload
* Application downtime
* Poor user experience

Load balancing solves this problem by distributing traffic across multiple backend resources.

---

## 3. How Load Balancing Works

The load balancer acts as an intermediate layer between users and backend servers.

### Request Flow

```text
Client
   |
   v
Load Balancer
   |
   +----------+----------+
   |          |          |
   v          v          v
Server 1   Server 2   Server 3
```

The load balancer:

1. Receives the client's request.
2. Checks the available backend servers.
3. Selects a suitable healthy server.
4. Forwards the request to that server.
5. Returns the server's response to the client.

---

## 4. Components of Load Balancing

### 4.1 Client

The client is the user or application that sends requests to the application.

Examples:

* Web browser
* Mobile application
* API client

### 4.2 Load Balancer

The load balancer receives incoming traffic and distributes it across backend resources.

### 4.3 Backend Servers

Backend servers process the requests received from the load balancer.

They may be:

* Virtual machines
* Physical servers
* Containers
* Application instances

### 4.4 Health Checks

Health checks determine whether backend resources are healthy and able to process requests.

If a server becomes unhealthy, the load balancer can stop sending traffic to it.

---

## 5. Types of Load Balancing

### 5.1 Network Load Balancing

Network load balancing operates mainly at the transport/network level.

It commonly handles:

* TCP traffic
* UDP traffic
* High-volume network connections

It is useful when high performance and low latency are required.

---

### 5.2 Application Load Balancing

Application load balancing operates at the application layer.

It commonly handles:

* HTTP
* HTTPS
* Web applications
* REST APIs

It can route traffic based on information such as:

* URL path
* Hostname
* HTTP headers
* Cookies

### Example

```text
example.com/products
        |
        v
Product Server

example.com/orders
        |
        v
Order Server
```

---

### 5.3 Global Load Balancing

Global load balancing distributes traffic between resources located in different geographic regions.

### Example

```text
                    Users
                      |
                      v
              Global Load Balancer
                 /           \
                v             v
          India Region     US Region
               |               |
          App Servers      App Servers
```

This can improve:

* Global availability
* Performance
* Latency
* Disaster resilience

---

## 6. Load Balancing Algorithms

A load balancing algorithm determines which backend server should receive a request.

### 6.1 Round Robin

Requests are distributed sequentially among available servers.

```text
Request 1 → Server 1
Request 2 → Server 2
Request 3 → Server 3
Request 4 → Server 1
Request 5 → Server 2
```

It is simple and works well when servers have similar capacity.

---

### 6.2 Weighted Round Robin

Each server is assigned a weight.

Servers with higher weights receive more traffic.

Example:

```text
Server 1 → Weight 5
Server 2 → Weight 3
Server 3 → Weight 2
```

Server 1 receives more requests than Server 2 and Server 3.

---

### 6.3 Least Connections

The load balancer sends the request to the server that currently has the fewest active connections.

This is useful when requests require different amounts of processing time.

---

### 6.4 IP Hash

The client's IP address is used to determine which backend server receives the request.

This can help maintain session consistency.

---

### 6.5 Least Response Time

Traffic is directed toward servers that provide faster responses.

This can help improve application performance.

---

## 7. Health Checks

Health checks are used to determine whether backend resources are working correctly.

For example:

```text
                 Load Balancer
                 /     |      \
                /      |       \
               v       v        v
          Server 1  Server 2  Server 3
             ✅        ❌        ✅
```

If Server 2 becomes unhealthy, the load balancer stops sending new requests to it.

```text
                 Load Balancer
                 /            \
                v              v
           Server 1         Server 3
              ✅                ✅
```

Health checks improve reliability and fault tolerance.

---

## 8. Load Balancing and High Availability

High availability means keeping an application available even when some components fail.

Without load balancing:

```text
Users
  |
  v
Single Server
  |
  X
Server Failure
  |
  X
Application Unavailable
```

With load balancing:

```text
                  Users
                    |
                    v
              Load Balancer
              /     |      \
             v      v       v
          Server 1 Server 2 Server 3
             ✅       ❌       ✅
```

Traffic can continue through the healthy servers.

---

## 9. Load Balancing and Scalability

Load balancing makes it easier to scale applications horizontally.

### Without Load Balancing

```text
Users
  |
  v
Server
```

### With Multiple Servers

```text
                  Users
                    |
                    v
              Load Balancer
             /      |      \
            v       v       v
        Server 1 Server 2 Server 3
```

More servers can be added when demand increases.

---

## 10. Load Balancing and Auto Scaling

Load balancing and auto scaling are different concepts but are commonly used together.

### Load Balancing

Responsible for:

* Distributing traffic
* Routing requests
* Detecting unhealthy servers
* Improving availability

### Auto Scaling

Responsible for:

* Adding resources when demand increases
* Removing resources when demand decreases
* Maintaining the required capacity

### Combined Architecture

```text
                  Users
                    |
                    v
              Load Balancer
                    |
          +---------+---------+
          |         |         |
          v         v         v
       Server 1  Server 2  Server 3
          ↑         ↑         ↑
          +---------+---------+
                    |
               Auto Scaling
```

Auto scaling changes the number of resources, while load balancing distributes traffic among them.

---

## 11. Benefits of Cloud Load Balancing

### High Availability

Applications can continue operating even if one backend server fails.

### Scalability

Traffic can be distributed across multiple servers.

### Fault Tolerance

The application can tolerate failure of individual backend resources.

### Better Performance

Traffic is distributed instead of overwhelming a single server.

### Improved Resource Utilization

Multiple servers can be used efficiently.

### Better User Experience

Users can receive faster and more reliable responses.

### Flexibility

Applications can run across multiple instances and, in some architectures, multiple regions.

---

## 12. Cloud Load Balancing Services

### AWS

AWS provides Elastic Load Balancing (ELB).

Major types include:

* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* Gateway Load Balancer (GWLB)

### Microsoft Azure

Azure provides:

* Azure Load Balancer
* Azure Application Gateway
* Azure Front Door

### Google Cloud

Google Cloud provides:

* Cloud Load Balancing

---

## 13. Application Load Balancer vs Network Load Balancer

| Feature          | Application Load Balancer | Network Load Balancer       |
| ---------------- | ------------------------- | --------------------------- |
| Layer            | Application Layer         | Transport/Network Layer     |
| Common Protocols | HTTP/HTTPS                | TCP/UDP                     |
| Routing          | Content-based routing     | Connection-based routing    |
| Use Case         | Web applications          | High-performance networking |
| Routing Rules    | Advanced                  | More network-focused        |

---

## 14. Load Balancer vs Reverse Proxy

A load balancer distributes traffic among multiple backend resources.

A reverse proxy acts as an intermediary between clients and backend servers and can provide features such as:

* Request forwarding
* SSL/TLS termination
* Caching
* Security
* Traffic routing

A load balancer can also perform reverse-proxy functions, depending on its architecture.

---

## 15. Real-World Example

Consider an online shopping website.

During normal traffic:

```text
                  Users
                    |
                    v
              Load Balancer
               /    |    \
              v     v     v
           Server Server Server
              1      2      3
```

During a sale, traffic increases significantly.

Auto scaling can create additional servers:

```text
                  Users
                    |
                    v
              Load Balancer
          /      /   |   \      \
         v      v    v    v      v
      Server  Server Server Server Server
        1       2      3      4      5
```

The load balancer distributes traffic among the available healthy servers.

---

## 16. Advantages

* Improves application availability
* Distributes incoming traffic
* Prevents server overload
* Supports horizontal scaling
* Provides fault tolerance
* Performs health checks
* Improves application performance
* Supports highly available architectures

---

## 17. Limitations

Load balancing also introduces some challenges:

* Additional infrastructure
* Additional configuration
* Additional cost
* Requires monitoring
* Incorrect configuration can cause routing problems
* Session management may require additional design

---

## 18. Important Terms

### Backend

The servers or resources receiving traffic from the load balancer.

### Frontend

The interface or endpoint through which users connect.

### Health Check

A test used to determine whether a backend resource is healthy.

### Listener

A component that checks for incoming connection requests on a specified protocol and port.

### Target

A backend resource that receives traffic from the load balancer.

### Traffic Routing

The process of deciding where incoming requests should be sent.

### Fault Tolerance

The ability of a system to continue operating when some components fail.

### High Availability

The ability of an application to remain accessible and operational for a high percentage of time.

---

## 19. Key Takeaways

* Load balancing distributes traffic across multiple backend resources.
* It improves availability, scalability, and performance.
* Health checks identify unhealthy backend servers.
* Round Robin distributes requests sequentially.
* Weighted Round Robin considers server capacity.
* Least Connections sends traffic to servers with fewer active connections.
* Load balancing and auto scaling are different but complementary.
* Application load balancing is commonly used for HTTP/HTTPS applications.
* Network load balancing is suitable for high-performance network traffic.
* Global load balancing can distribute traffic across geographic regions.
* Cloud providers offer managed load balancing services.

---

## 20. Interview Questions

### Q1. What is cloud load balancing?

Cloud load balancing is the process of distributing incoming traffic across multiple cloud resources to improve performance, availability, and scalability.

### Q2. Why is load balancing important?

It prevents individual servers from becoming overloaded and helps applications remain available when backend resources fail.

### Q3. What is a health check?

A health check verifies whether a backend resource is healthy and capable of processing requests.

### Q4. What happens if a backend server fails?

The load balancer detects the unhealthy server and stops routing new traffic to it.

### Q5. What is Round Robin?

Round Robin distributes requests sequentially across available servers.

### Q6. What is the difference between load balancing and auto scaling?

Load balancing distributes traffic, whereas auto scaling dynamically increases or decreases the number of resources based on demand.

### Q7. What is application load balancing?

Application load balancing routes application-level traffic such as HTTP/HTTPS requests and can make decisions based on application information.

### Q8. What is network load balancing?

Network load balancing handles network-level traffic such as TCP or UDP and is designed for high performance and low latency.

### Q9. What is high availability?

High availability is the ability of a system to remain operational and accessible even when some components fail.

### Q10. Name some cloud load balancing services.

Examples include AWS Elastic Load Balancing, Azure Load Balancer, Azure Application Gateway, Azure Front Door, and Google Cloud Load Balancing.

---

## 21. Day 31 Practical Learning

For practical understanding:

1. Study the architecture of a cloud load balancer.
2. Understand different load balancing algorithms.
3. Learn how health checks work.
4. Understand the relationship between load balancing and auto scaling.
5. Explore AWS Elastic Load Balancing, Azure Load Balancer, or Google Cloud Load Balancing.
6. Create a simple load-balancing architecture diagram.
7. Review the difference between Application and Network Load Balancers.
8. Add these notes to the Cloud Learning Journey GitHub repository.

---

## 22. Summary

Cloud Load Balancing is an important cloud architecture concept that distributes incoming traffic across multiple backend resources. It helps applications handle large numbers of users while improving performance, availability, scalability, and fault tolerance.

Load balancing becomes especially powerful when combined with auto scaling, health checks, monitoring, and highly available architectures.

**Day 31 Completed: Cloud Load Balancing**
