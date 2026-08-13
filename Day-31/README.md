#  Day 31 – Cloud Load Balancing

Welcome to **Day 31** of my **50-Day Cloud Learning Journey**.

Today I learned about **Cloud Load Balancing**, an important cloud computing concept used to distribute incoming traffic across multiple servers or application instances.

---

##  Topic Covered

### Cloud Load Balancing

Load balancing distributes incoming network traffic across multiple backend resources to prevent individual servers from becoming overloaded.

It helps improve:

* High Availability
* Scalability
* Performance
* Fault Tolerance
* Reliability
* Resource Utilization

---

##  Learning Objectives

By the end of Day 31, I learned:

* What cloud load balancing is
* Why load balancing is required
* How a load balancer works
* Components of a load balancing architecture
* Types of load balancing
* Load balancing algorithms
* Health checks
* Load balancing and high availability
* Load balancing and scalability
* Load balancing vs auto scaling
* Application Load Balancer vs Network Load Balancer
* Cloud load balancing services
* Advantages and limitations of load balancing

---

##  Basic Load Balancing Architecture

```text
                    Users
                      |
                      v
                Load Balancer
                 /     |     \
                v      v      v
            Server 1 Server 2 Server 3
```

The load balancer receives incoming requests and distributes them across healthy backend servers.

---

##  How Load Balancing Works

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

The general process is:

1. Client sends a request.
2. Load balancer receives the request.
3. Load balancer checks available backend resources.
4. A healthy backend server is selected.
5. Request is forwarded to that server.
6. Server processes the request.
7. Response is returned to the client.

---

## 🔍 Types of Load Balancing

### 1. Network Load Balancing

Handles network-level traffic such as:

* TCP
* UDP

It is useful for applications requiring high performance and low latency.

### 2. Application Load Balancing

Works at the application layer and commonly handles:

* HTTP
* HTTPS

It can route traffic based on:

* URL path
* Hostname
* HTTP headers
* Cookies

### 3. Global Load Balancing

Distributes traffic between resources located in different geographic regions.

---

## Load Balancing Algorithms

I learned about the following algorithms:

### Round Robin

Requests are distributed sequentially.

```text
Request 1 → Server 1
Request 2 → Server 2
Request 3 → Server 3
Request 4 → Server 1
```

### Weighted Round Robin

Servers receive traffic according to their assigned weights.

### Least Connections

Traffic is sent to the server with the fewest active connections.

### IP Hash

The client's IP address is used to determine the backend server.

### Least Response Time

Traffic can be directed toward servers providing faster responses.

---

## ❤️ Health Checks

Load balancers use health checks to determine whether backend servers are available.

```text
Load Balancer
   |
   +---- Server 1 ✅
   |
   +---- Server 2 ❌
   |
   +---- Server 3 ✅
```

If Server 2 becomes unhealthy, the load balancer stops sending new requests to it.

---

##  Load Balancing and Auto Scaling

Load balancing and auto scaling perform different functions.

| Load Balancing         | Auto Scaling                |
| ---------------------- | --------------------------- |
| Distributes traffic    | Changes number of resources |
| Routes requests        | Adds/removes instances      |
| Improves availability  | Adjusts capacity            |
| Performs health checks | Responds to changing demand |

They are commonly used together in cloud architectures.

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

---

## ☁️ Cloud Load Balancing Services

### AWS

* Elastic Load Balancing (ELB)
* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* Gateway Load Balancer (GWLB)

### Microsoft Azure

* Azure Load Balancer
* Azure Application Gateway
* Azure Front Door

### Google Cloud

* Cloud Load Balancing

---

## 📊 Application Load Balancer vs Network Load Balancer

| Feature     | Application Load Balancer | Network Load Balancer       |
| ----------- | ------------------------- | --------------------------- |
| Layer       | Application Layer         | Transport/Network Layer     |
| Protocols   | HTTP/HTTPS                | TCP/UDP                     |
| Routing     | Content-based             | Connection-based            |
| Main Use    | Web applications          | High-performance networking |
| Performance | Application-aware         | High performance            |

---

##  Benefits

* Improves availability
* Prevents server overload
* Supports horizontal scaling
* Improves application performance
* Provides fault tolerance
* Performs health checks
* Improves resource utilization
* Supports highly available architectures

---

## Challenges

* Additional infrastructure
* Additional configuration
* Additional cost
* Requires monitoring
* Incorrect configuration can cause routing issues
* Session management may require additional design

---

##  Real-World Example

Consider an online shopping application.

During normal traffic:

```text
Users
  |
  v
Load Balancer
 /    |    \
v     v     v
S1    S2    S3
```

During a sale, traffic increases and additional servers can be added through auto scaling:

```text
Users
  |
  v
Load Balancer
 /   |   |   |   \
v    v   v   v    v
S1   S2  S3  S4   S5
```

The load balancer distributes requests across the available healthy servers.

---

##  Key Takeaways

* Load balancing distributes traffic across multiple backend resources.
* It helps prevent server overload.
* Health checks identify unhealthy servers.
* Load balancing improves availability and fault tolerance.
* Round Robin is a simple traffic distribution algorithm.
* Least Connections considers active connections.
* Application Load Balancers handle application-level traffic.
* Network Load Balancers handle network-level traffic.
* Load balancing and auto scaling are different but complementary.
* Cloud providers offer managed load balancing services.

---

##  Interview Preparation

### What is Cloud Load Balancing?

Cloud Load Balancing distributes incoming traffic across multiple backend resources to improve performance, scalability, and availability.

### Why do we need Load Balancing?

To prevent server overload, improve application availability, distribute traffic efficiently, and provide fault tolerance.

### What is a Health Check?

A health check verifies whether a backend server is healthy and capable of processing requests.

### What happens when a server fails?

The load balancer detects the unhealthy server and stops routing new requests to it.

### Load Balancing vs Auto Scaling?

Load balancing distributes traffic, while auto scaling dynamically changes the number of resources based on demand.

---

## 🛠️ Practical Learning

During Day 31, I focused on:

* Understanding load balancing architecture
* Studying load balancing algorithms
* Understanding health checks
* Learning Application vs Network Load Balancing
* Understanding load balancing with auto scaling
* Exploring cloud load balancing services
* Understanding high availability and fault tolerance

---


## Skills & Concepts Learned

`Cloud Computing` `Load Balancing` `High Availability` `Fault Tolerance` `Scalability` `Health Checks` `Traffic Routing` `Auto Scaling` `AWS ELB` `Azure Load Balancer` `Google Cloud Load Balancing`

---

##  Day 31 Status

* [x] Learned Cloud Load Balancing
* [x] Understood load balancing architecture
* [x] Learned load balancing algorithms
* [x] Learned health checks
* [x] Understood high availability
* [x] Understood load balancing vs auto scaling
* [x] Learned Application vs Network Load Balancing
* [x] Explored cloud load balancing services
* [x] Prepared interview questions
* [x] Added notes to GitHub

---

##  Next Step

**Day 32 – Cloud DNS & Traffic Routing**

Continuing the 50-Day Cloud Learning Journey.

---

### Progress

**Day 31 / 50 Completed ✅**

> Learning cloud computing one day at a time and building a strong foundation for real-world cloud engineering.
