# Cloud Security Architecture & Zero Trust 

##  Overview

Cloud Security Architecture is the design and implementation of security controls that protect cloud infrastructure, applications, networks, identities, and data.

Zero Trust is a modern security approach based on the principle:

> **Never Trust, Always Verify**

It assumes that no user, device, application, or network should automatically be trusted.

---

## Learning Objectives

- Understand Cloud Security Architecture
- Learn Defense in Depth
- Understand Zero Trust Architecture
- Learn the Principle of Least Privilege
- Understand cloud network security
- Learn data encryption concepts
- Understand security monitoring
- Learn the Shared Responsibility Model
- Understand cloud incident response

---

##  1. Cloud Security Architecture

Cloud Security Architecture protects:

- Applications
- Data
- Networks
- APIs
- Virtual Machines
- Containers
- Identities
- Cloud infrastructure

A secure architecture uses multiple security layers.

### Example

```text
Users
  ↓
Identity + MFA
  ↓
WAF / Firewall
  ↓
Load Balancer
  ↓
Application
  ↓
Database
  ↓
Encrypted Storage
  ↓
Monitoring & Logging
````

---

##  2. Defense in Depth

Defense in Depth means using multiple security mechanisms instead of depending on a single security control.

### Security Layers

```text
Layer 1 → Identity Security
Layer 2 → Network Security
Layer 3 → Application Security
Layer 4 → Data Security
Layer 5 → Monitoring & Detection
Layer 6 → Incident Response
```

If one security layer fails, other layers can help protect the system.

---

##  3. Zero Trust Architecture

Zero Trust follows:

> **Never Trust, Always Verify**

Traditional security often assumes that users inside a network are trusted.

Zero Trust continuously verifies access.

```text
Request
   ↓
Verify Identity
   ↓
Verify Device
   ↓
Check Permissions
   ↓
Evaluate Context
   ↓
Grant Minimum Required Access
   ↓
Monitor Activity
```

### Core Principles

1. Verify explicitly
2. Use least-privilege access
3. Assume breach
4. Continuously monitor
5. Protect resources instead of trusting the network

---

##  4. Principle of Least Privilege

Users and applications should receive only the permissions they actually need.

### Bad Practice

```text
Application → Full Cloud Administrator Access 
```

### Better Practice

```text
Application
    ↓
IAM Role
    ↓
Only Required Resources
```

Least privilege reduces the impact of compromised accounts.

---

## 5. Cloud Network Security

Important security mechanisms include:

* VPC / Virtual Network
* Public and Private Subnets
* Security Groups
* Network ACLs
* Firewalls
* VPN
* Private Endpoints
* WAF
* DDoS Protection

### Secure Architecture

```text
Internet
   ↓
WAF
   ↓
Load Balancer
   ↓
Application Subnet
   ↓
Private Database Subnet
```

Sensitive databases should generally not be directly accessible from the public internet.

---

##  6. Data Security

### Encryption at Rest

Protects data while it is stored.

Examples:

```text
Database → Encrypted Storage
Files → Encrypted Object Storage
```

### Encryption in Transit

Protects data while it moves between systems.

```text
Client
  ↓
HTTPS / TLS
  ↓
Server
```

### Key Management

Cloud platforms provide services for managing encryption keys.

Examples:

* AWS KMS
* Azure Key Vault
* Google Cloud KMS

---

##  7. Security Monitoring

Security monitoring helps detect suspicious activities.

Monitor:

* Login attempts
* API calls
* Network traffic
* Failed authentication
* Permission changes
* Configuration changes
* Suspicious activities
* Security alerts

### Monitoring Flow

```text
Cloud Resources
      ↓
Logs
      ↓
Monitoring
      ↓
Security Detection
      ↓
Alert
      ↓
Incident Response
```

---

##  8. Shared Responsibility Model

Cloud security is shared between the cloud provider and the customer.

### Cloud Provider

Usually responsible for:

* Physical data centers
* Physical hardware
* Networking infrastructure
* Core cloud infrastructure

### Customer

Usually responsible for:

* Data
* Identity and access
* Application security
* Cloud configuration
* Permissions
* Operating system security where applicable

The exact responsibility depends on the cloud service being used.

---

##  9. Incident Response

A cloud security incident should be handled systematically.

### Basic Process

```text
Detection
   ↓
Analysis
   ↓
Containment
   ↓
Eradication
   ↓
Recovery
   ↓
Lessons Learned
```

---

##  10. Important Cloud Security Practices

* Enable MFA
* Follow least privilege
* Use strong authentication
* Encrypt sensitive data
* Use HTTPS/TLS
* Keep databases private
* Use security groups and firewalls
* Monitor cloud activity
* Enable logging
* Protect secrets and credentials
* Regularly review permissions
* Keep systems updated
* Prepare an incident response plan

---

##  Zero Trust vs Traditional Security

| Traditional Security    | Zero Trust                                |
| ----------------------- | ----------------------------------------- |
| Trust internal network  | Do not automatically trust                |
| Network-centric         | Identity/resource-centric                 |
| One-time verification   | Continuous verification                   |
| Broad access            | Least-privilege access                    |
| Trust based on location | Trust based on authentication and context |

---

##  Practical Architecture

A secure cloud-hosted AI/Flask application can follow:

```text
                    Internet
                       ↓
                  WAF / DDoS
                       ↓
                Load Balancer
                       ↓
                Application
                       ↓
             ┌─────────┴─────────┐
             ↓                   ↓
        IAM / Roles          Monitoring
             ↓
       Private Database
             ↓
       Encrypted Storage
```

---

##  Interview Questions

### 1. What is Zero Trust?

Zero Trust is a security model that assumes no user, device, or application is automatically trusted and requires continuous verification.

### 2. What is Defense in Depth?

Defense in Depth uses multiple layers of security controls to protect systems against different types of threats.

### 3. What is Least Privilege?

Least Privilege means providing users and applications only the minimum permissions required to perform their tasks.

### 4. What is encryption at rest?

Encryption at rest protects data while it is stored.

### 5. What is encryption in transit?

Encryption in transit protects data while it is transferred between systems, commonly using TLS/HTTPS.

### 6. What is the Shared Responsibility Model?

It defines which security responsibilities belong to the cloud provider and which belong to the customer.

---

##  Key Takeaways

* Cloud security requires multiple layers of protection.
* Zero Trust follows "Never Trust, Always Verify."
* Least privilege reduces security risks.
* Encryption protects sensitive data.
* Private networking helps protect critical resources.
* Monitoring and logging are essential for detecting threats.
* Cloud security responsibilities are shared between providers and customers.

---

##  Day 43 Completed

**Topic:** Cloud Security Architecture & Zero Trust
**Focus:** Zero Trust, Defense in Depth, IAM, Network Security, Encryption, Monitoring and Shared Responsibility

````
