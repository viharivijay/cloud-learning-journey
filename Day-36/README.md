# Serverless Computing & AWS Lambda

> **Cloud Learning Journey — Day 36 of 50**

##  Topic

**Serverless Computing & AWS Lambda**

Today I learned how serverless computing allows developers to run application code without directly managing servers and how AWS Lambda provides event-driven serverless compute.

---

##  Learning Objectives

* Understand serverless computing
* Learn AWS Lambda fundamentals
* Understand Lambda functions
* Learn about Lambda triggers
* Understand event-driven architecture
* Learn API Gateway + Lambda architecture
* Understand Lambda scaling
* Learn about cold starts
* Understand Lambda Layers
* Learn about Lambda environment variables
* Understand serverless advantages and limitations
* Explore real-world serverless use cases

---

##  Topics Covered

### 1. Serverless Computing

* Definition of serverless
* Serverless architecture
* Automatic scaling
* Usage-based execution
* Event-driven applications
* Server management abstraction

### 2. AWS Lambda

* Lambda functions
* Lambda runtime
* Handler
* Event and context
* Function invocation
* Execution model

### 3. Lambda Triggers

Studied how Lambda can be triggered by:

* Amazon S3
* Amazon API Gateway
* Amazon EventBridge
* Amazon SQS
* Amazon DynamoDB Streams

### 4. Lambda Architecture

```text
Client
  ↓
API Gateway
  ↓
AWS Lambda
  ↓
Business Logic
  ↓
Database / Storage
```

### 5. Lambda Features

* Automatic scaling
* Lambda Layers
* Environment variables
* CloudWatch integration
* IAM-based permissions
* Event-driven execution

### 6. Cold Starts

Learned why Lambda may experience additional latency when a new execution environment needs to be initialized.

### 7. Serverless Use Cases

* REST APIs
* File processing
* Image processing
* Automation
* Data processing
* Scheduled tasks
* Event-driven applications
* Backend services

---

##  Serverless vs Traditional Servers

| Feature                    | Traditional                | Serverless              |
| -------------------------- | -------------------------- | ----------------------- |
| Server management          | Required                   | Managed by provider     |
| Scaling                    | Configured by organization | Automatically managed   |
| Billing                    | Provisioned resources      | Usage-based             |
| Infrastructure maintenance | Required                   | Mostly provider-managed |
| Execution                  | Often continuously running | Commonly event-driven   |

---

##  Key Takeaways

* Serverless still uses servers, but the cloud provider manages them.
* AWS Lambda executes code in response to events.
* Lambda can automatically scale based on demand.
* API Gateway and Lambda are commonly used together to build serverless APIs.
* Lambda functions are generally designed to be stateless.
* Cold starts can affect application latency.
* CloudWatch helps monitor Lambda functions.
* IAM controls Lambda permissions and access.

---

##  Example Architecture

```text
             User
               ↓
        Amazon API Gateway
               ↓
          AWS Lambda
               ↓
       ┌───────┴───────┐
       ↓               ↓
   DynamoDB           S3
```

---

##  Interview Preparation

### Questions Practiced

1. What is serverless computing?
2. What is AWS Lambda?
3. What is a Lambda trigger?
4. What is a Lambda cold start?
5. How does Lambda scale?
6. What is a Lambda Layer?
7. Why are Lambda functions generally stateless?
8. How does API Gateway work with Lambda?
9. What are the advantages of serverless computing?
10. What are the limitations of serverless architecture?

---

# Progress

**Day:** 36 / 50

**Status:**  Completed

### Previous Topic

**Day 35 — Cloud CDN**

### Current Topic

**Day 36 — Serverless Computing & AWS Lambda**

### Next

**Day 37 — Event-Driven Architecture & Cloud Messaging**

---



##  Conclusion

Day 36 helped me understand how serverless computing abstracts infrastructure management and how AWS Lambda can be used to build scalable, event-driven applications.

The next step is to understand how cloud applications communicate through **events, queues, and messaging systems**.
