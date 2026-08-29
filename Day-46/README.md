# Cloud API Management

##  Overview

Day 46 of my **50-Day Cloud Learning Journey** focused on **Cloud API Management** and how APIs are securely exposed, managed, monitored, and controlled in cloud environments.

I learned about **API Gateways, REST APIs, authentication, authorization, rate limiting, throttling, caching, API versioning, and API security**, along with cloud services such as **AWS API Gateway** and **Azure API Management**.

---

##  Learning Objectives

* Understand APIs and API Management
* Learn the role of an API Gateway
* Understand REST API methods
* Learn authentication and authorization
* Understand rate limiting and throttling
* Learn API versioning and caching
* Understand API security
* Explore AWS API Gateway and Azure API Management
* Understand real-world API architecture

---

##  Topics Covered

### 🔹 API Fundamentals

* What is an API?
* API request and response
* REST APIs
* HTTP methods

### 🔹 API Gateway

* API Gateway architecture
* Request routing
* Authentication
* Authorization
* Traffic management
* Monitoring and logging

### 🔹 API Management

* API publishing
* API security
* API lifecycle management
* API versioning
* Analytics and monitoring

### 🔹 Traffic Management

* Rate limiting
* Throttling
* Caching

### 🔹 API Security

* HTTPS/TLS
* API keys
* JWT
* OAuth 2.0
* IAM
* Input validation
* WAF

### ☁️ Cloud Services

* Amazon API Gateway
* Azure API Management

---

## API Architecture

```text
                    Users
                      ↓
                 API Gateway
                      ↓
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
    Auth API      Product API    Order API
        ↓             ↓             ↓
    Database      Database      Database
                      ↓
                  Cache Layer
```

---

##  API Request Flow

```text
Client
  ↓
HTTPS Request
  ↓
API Gateway
  ↓
Authentication
  ↓
Authorization
  ↓
Rate Limiting
  ↓
Backend Service
  ↓
Database
  ↓
Response
```

---

##  Practical Learning

As part of the practical learning, I explored how a REST API can be designed using **Flask/FastAPI** and how an API Gateway can be placed between the client and backend service.

Example endpoints:

```text
GET    /products
GET    /products/<id>
POST   /products
PUT    /products/<id>
DELETE /products/<id>
```

---

##  Key Takeaways

* APIs allow different software systems to communicate.
* API Management provides centralized control over APIs.
* API Gateways act as entry points for client requests.
* Authentication verifies user identity.
* Authorization controls access permissions.
* Rate limiting prevents excessive API usage.
* Throttling protects backend services from overload.
* Caching improves API performance.
* API versioning helps maintain backward compatibility.
* API security is essential for protecting cloud applications.

---

##  Interview Preparation

### What is an API Gateway?

An API Gateway is a centralized entry point that receives client requests and routes them to appropriate backend services while providing capabilities such as authentication, authorization, rate limiting, monitoring, and caching.

### Authentication vs Authorization

**Authentication** determines who the user is, while **authorization** determines what the authenticated user is allowed to access.

### Rate Limiting vs Throttling

**Rate limiting** restricts the number of requests a client can make, while **throttling** controls the rate at which requests are processed.

---

##  Technologies & Concepts

`API` `REST` `API Gateway` `API Management` `AWS` `Azure` `Authentication` `Authorization` `JWT` `OAuth 2.0` `Rate Limiting` `Throttling` `Caching` `API Security`

---

##  Learning Progress

**Cloud Learning Journey: 46/50 Days Completed**

```text
██████████████████████████████████████████████░░░░ 92%
```

---

##  Goal

Continue building practical cloud knowledge and develop the ability to **design, deploy, secure, monitor, and explain production-ready cloud applications**.

**46 days completed. 4 days to go! ☁️🚀**
