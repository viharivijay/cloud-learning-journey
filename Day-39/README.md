# Event-Driven Architecture


##  Overview

**Event-Driven Architecture (EDA)** is a software architecture pattern where services communicate through **events** instead of relying only on direct request-response communication.

An event represents something that has happened, such as `OrderCreated`, `PaymentCompleted`, or `UserRegistered`.

```text
Producer → Event Broker → Consumers
              ↓
       Multiple Services
```

##  Topics Covered

* Event Producers & Consumers
* Event Brokers
* Publish/Subscribe
* Message Queues
* Event Streaming
* Event Schemas
* Event Ordering
* At-Most-Once & At-Least-Once Delivery
* Idempotency
* Retry Mechanisms
* Dead-Letter Queues
* Event Replay
* Event Sourcing
* CQRS
* Saga Pattern
* Eventual Consistency
* Event-Driven Microservices
* Cloud Event Services

## ☁️ Cloud Services

| AWS         | Azure       | Google Cloud |
| ----------- | ----------- | ------------ |
| EventBridge | Event Grid  | Pub/Sub      |
| SNS         | Service Bus | Eventarc     |
| SQS         | Event Hubs  | —            |
| Kinesis     | —           | —            |

##  Example Architecture

```text
                    Customer
                       |
                       ↓
                 Order Service
                       |
                 OrderCreated
                       |
                       ↓
                 Event Broker
                /      |       \
               ↓       ↓        ↓
           Payment  Inventory  Notification
           Service   Service     Service
```

##  Key Concepts

**Event:** A record of something that happened.

**Producer:** Service that generates an event.

**Consumer:** Service that processes an event.

**Event Broker:** Infrastructure that routes or distributes events.

**Idempotency:** Processing the same event multiple times does not create an unintended additional effect.

**Dead-Letter Queue:** Stores events that repeatedly fail processing.

**Eventual Consistency:** Distributed services may temporarily have different states before converging.

**Event Sourcing:** Stores state changes as a sequence of events.

**CQRS:** Separates read and write responsibilities.

**Saga:** Coordinates distributed business workflows using local transactions and compensating actions.

##  Benefits

* Loose coupling
* Independent scalability
* Asynchronous processing
* Better resilience
* Real-time processing
* Easy integration between services
* Suitable for microservices and serverless applications

##  Challenges

* Distributed debugging
* Eventual consistency
* Duplicate events
* Event ordering
* Schema evolution
* Monitoring complexity
* Distributed transactions

##  Key Takeaway

> **Event-Driven Architecture enables scalable and loosely coupled distributed systems by allowing services to communicate through events.**

##  Learning Outcome

After completing **Day 49**, I learned how Event-Driven Architecture works and how **events, brokers, queues, streaming, microservices, serverless, Event Sourcing, CQRS, Saga, retries, and DLQs** are used to build modern cloud-native applications.

##  References

* [AWS Event-Driven Architecture](https://aws.amazon.com/event-driven-architecture/)
* [Azure Event-Driven Architecture](https://learn.microsoft.com/azure/architecture/guide/architecture-styles/event-driven)
* [Google Cloud Pub/Sub](https://cloud.google.com/pubsub/docs/overview)
* [Apache Kafka](https://kafka.apache.org/documentation/)

###  Tags

`#CloudComputing` `#EventDrivenArchitecture` `#Microservices` `#AWS` `#Azure` `#GCP` `#Kafka` `#CloudNative` `#DevOps`
