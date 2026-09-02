#  Cloud Security Architecture & Zero Trust

##  Overview

Cloud Security Architecture is the design and implementation of security controls that protect cloud-based applications, infrastructure, identities, networks, and data.

Modern cloud security focuses on **Zero Trust, least privilege, identity-based access, encryption, network security, continuous monitoring, and automated threat response**.

---

##  Learning Objectives

* Understand cloud security architecture
* Learn the Shared Responsibility Model
* Understand Zero Trust Architecture
* Learn IAM fundamentals
* Understand authentication and authorization
* Learn cloud network security
* Understand data encryption
* Learn secrets management
* Understand cloud security monitoring
* Explore DevSecOps practices

---

## 1.  Shared Responsibility Model

Cloud security responsibilities are divided between the cloud provider and the customer.

### Cloud Provider Responsibilities

The provider is responsible for security **of the cloud**:

* Physical data centers
* Physical servers
* Networking infrastructure
* Storage infrastructure
* Hypervisor
* Core cloud infrastructure

### Customer Responsibilities

The customer is responsible for security **in the cloud**:

* Applications
* Data
* IAM
* Access policies
* Network configuration
* Operating system configuration
* Secrets
* Security settings

```text
             Cloud Security
                   │
        ┌──────────┴──────────┐
        │                     │
   Cloud Provider          Customer
        │                     │
 Physical Infrastructure   Applications
 Networking                Data
 Hypervisor                IAM
 Storage                   Secrets
```

---

# 2.  Zero Trust Architecture

Zero Trust follows the principle:

> **Never trust, always verify.**

Traditional security often assumes that users inside a trusted network can be trusted.

Zero Trust continuously verifies access requests.

```text
User / Device
      │
      ▼
Identity Verification
      │
      ▼
Context & Risk Check
      │
      ▼
Authorization
      │
 ┌────┴────┐
 ▼         ▼
Allow     Deny
```

### Core Principles

1. **Verify explicitly**
2. **Use least privilege**
3. **Assume breach**

---

# 3.  Identity and Access Management (IAM)

IAM controls who can access cloud resources and what actions they can perform.

```text
WHO
 │
 ▼
CAN DO WHAT
 │
 ▼
ON WHICH RESOURCE
```

### Common IAM Components

| Component | Purpose                    |
| --------- | -------------------------- |
| User      | Individual identity        |
| Group     | Collection of users        |
| Role      | Temporary/assumed identity |
| Policy    | Defines permissions        |
| MFA       | Additional authentication  |

### Example

```text
Developer
    │
    ▼
IAM Role
    │
    ▼
Read Application Logs
    │
    └──  Cannot Delete Production Database
```

---

# 4.  Authentication vs Authorization

### Authentication

Authentication answers:

> **Who are you?**

Examples:

* Username and password
* MFA
* SSO
* Biometrics

### Authorization

Authorization answers:

> **What are you allowed to do?**

Example:

```text
Authenticated User
       │
       ├── Read Database       
       ├── Read Logs           
       └── Delete Database     
```

### Easy way to remember

```text
Authentication → Identity
Authorization  → Permissions
```

---

# 5.  Multi-Factor Authentication

MFA requires more than one authentication factor.

### Factors

**Something you know**

* Password
* PIN

**Something you have**

* Mobile device
* Authenticator
* Security key

**Something you are**

* Fingerprint
* Face recognition

```text
Password
   +
Authenticator Code
   ↓
Access Granted
```

---

# 6.  Principle of Least Privilege

Least privilege means giving users and services **only the permissions they require**.

###  Bad

```text
Developer → Administrator
```

###  Better

```text
Developer
   │
   ├── Deploy Application
   ├── Read Logs
   └── View Monitoring
```

Without unnecessary permissions such as:

```text
 Delete Database
 Modify IAM
 Access Sensitive Data
```

### Benefits

* Reduces attack surface
* Limits accidental changes
* Reduces impact of compromised accounts
* Improves security

---

# 7.  Cloud Network Security

Important cloud network security controls include:

* VPC / VNet
* Subnets
* Security Groups
* Network ACLs
* Firewalls
* WAF
* VPN
* Private endpoints
* Network segmentation

### Example Architecture

```text
                 Internet
                    │
                    ▼
                   WAF
                    │
                    ▼
             Load Balancer
                    │
                    ▼
          Application Subnet
                    │
                    ▼
             Database Subnet
```

The database should generally not be directly exposed to the public internet.

---

# 8.  Web Application Firewall (WAF)

A WAF protects web applications from malicious HTTP/HTTPS traffic.

It can help protect against attacks such as:

* SQL Injection
* Cross-Site Scripting (XSS)
* Malicious HTTP requests
* Suspicious bots
* Known attack patterns

```text
Internet
    │
    ▼
   WAF
    │
    ▼
Load Balancer
    │
    ▼
Application
```

---

# 9.  Data Security

Cloud data should be protected both **at rest** and **in transit**.

### Data at Rest

Data stored in:

* Databases
* Object storage
* Disks
* Backups

should be encrypted when appropriate.

### Data in Transit

Data moving between systems should use secure protocols such as:

* HTTPS
* TLS
* VPN

```text
User
 │
 │ HTTPS / TLS
 ▼
Application
 │
 │ Encrypted Connection
 ▼
Database
```

---

# 10.  Secrets Management

Sensitive credentials should never be hardcoded in application source code.

###  Bad

```python
username = "admin"
password = "mypassword"
api_key = "secret-key"
```

###  Better

```text
Application
     │
     ▼
Secrets Manager
     │
     ▼
Credentials
```

Examples of secret-management solutions:

* AWS Secrets Manager
* Azure Key Vault
* Google Secret Manager
* HashiCorp Vault

### Benefits

* Secure credential storage
* Access control
* Secret rotation
* Reduced credential exposure

---

# 11.  Cloud Security Monitoring

Cloud environments require continuous monitoring.

Important sources include:

* Application logs
* Network logs
* IAM logs
* Audit logs
* Infrastructure logs

```text
Application Logs ──┐
Network Logs ──────┤
IAM Logs ──────────┤
Audit Logs ────────┤
                   ▼
          Security Monitoring
                   │
                   ▼
                 Alert
                   │
                   ▼
             Investigation
                   │
                   ▼
               Response
```

### Examples of suspicious behavior

* Multiple failed login attempts
* Login from unusual locations
* Privilege escalation
* Unexpected resource creation
* Large data downloads
* Unauthorized API activity

---

# 12.  Security Automation

Security responses can be automated.

Example:

```text
Suspicious Activity
        │
        ▼
Security Detection
        │
        ▼
Automated Response
        │
        ├── Disable Session
        ├── Block Access
        ├── Isolate Resource
        └── Send Alert
```

Automation helps reduce **Mean Time to Respond (MTTR)**.

---

# 13.  DevSecOps

DevSecOps integrates security throughout the software development lifecycle.

### Traditional Approach

```text
Code
  ↓
Build
  ↓
Test
  ↓
Deploy
  ↓
Security Check
```

### DevSecOps

```text
Plan
 ↓
Code
 ↓
Security Scan
 ↓
Build
 ↓
Test
 ↓
Dependency Scan
 ↓
Container Scan
 ↓
Deploy
 ↓
Monitor
```

### Benefits

* Finds vulnerabilities earlier
* Reduces security risks
* Automates security testing
* Improves software quality
* Supports secure continuous delivery

---

# 14. Secure Cloud Architecture

A basic secure cloud application can follow this structure:

```text
                    Internet
                       │
                       ▼
                     WAF
                       │
                       ▼
                Load Balancer
                       │
              ┌────────┴────────┐
              ▼                 ▼
        Application 1     Application 2
              │                 │
              └────────┬────────┘
                       ▼
                 Private Network
                       │
                       ▼
                    Database
                       │
                       ▼
              Encrypted Storage
```

Security controls can be applied at every layer.

---

# 15.  Cloud Security Best Practices

## Identity

* Enable MFA
* Apply least privilege
* Avoid shared accounts
* Use temporary credentials
* Regularly review permissions

## Network

* Use private subnets
* Restrict inbound traffic
* Use WAF
* Segment workloads
* Avoid public database access

## Data

* Encrypt sensitive data
* Encrypt backups
* Protect encryption keys
* Implement access controls

## Secrets

* Use a secrets manager
* Never hardcode credentials
* Rotate secrets
* Restrict secret access

## Monitoring

* Centralize logs
* Monitor IAM activity
* Configure security alerts
* Maintain audit trails
* Automate incident responses

---

#  Key Takeaways

```text
Cloud Security
      │
      ├── Shared Responsibility
      │
      ├── Zero Trust
      │    ├── Verify Explicitly
      │    ├── Least Privilege
      │    └── Assume Breach
      │
      ├── IAM
      │    ├── Authentication
      │    ├── Authorization
      │    └── MFA
      │
      ├── Network Security
      │    ├── Firewall
      │    ├── WAF
      │    └── Segmentation
      │
      ├── Data Security
      │    ├── Encryption at Rest
      │    └── Encryption in Transit
      │
      ├── Secrets Management
      │
      ├── Security Monitoring
      │
      └── DevSecOps
```

---

#  Interview Questions

### 1. What is Zero Trust?

Zero Trust is a security model where no user, device, or service is automatically trusted. Access requests are verified and authorized continuously.

### 2. What is least privilege?

Least privilege means providing an identity or service with only the minimum permissions required to perform its task.

### 3. What is IAM?

IAM is a framework for managing identities and controlling access to cloud resources.

### 4. What is the difference between authentication and authorization?

Authentication verifies **who you are**, while authorization determines **what you are allowed to do**.

### 5. Why should secrets not be stored in source code?

Source code can be exposed through repositories, logs, or accidental sharing. Dedicated secret-management systems provide controlled access, encryption, and rotation.

### 6. What is a WAF?

A Web Application Firewall filters and protects web application traffic against common web-based attacks.

### 7. What is the Shared Responsibility Model?

It defines security responsibilities between the cloud provider and customer. The provider secures the underlying cloud infrastructure, while the customer secures their workloads, identities, configurations, and data.

### 8. What is DevSecOps?

DevSecOps integrates security into the complete software development lifecycle rather than treating security as a final-stage activity.

---

#  Day 49 Summary

| Area                  | What I Learned                        |
| --------------------- | ------------------------------------- |
| Cloud Security        | Security architecture and controls    |
| Shared Responsibility | Provider vs customer responsibilities |
| Zero Trust            | Never trust, always verify            |
| IAM                   | Identity and access management        |
| MFA                   | Multi-factor authentication           |
| Least Privilege       | Minimum required permissions          |
| Network Security      | WAF, firewalls, segmentation          |
| Data Security         | Encryption at rest and transit        |
| Secrets               | Secure credential management          |
| Monitoring            | Continuous security monitoring        |
| Automation            | Automated threat response             |
| DevSecOps             | Security throughout SDLC              |

---

## Progress

**Cloud Learning Journey: 49/50 Days Completed**

### Next: Day 50 🎓

Final milestone:

> **Build a Production-Grade Cloud Architecture Capstone**

The final project will combine:

**Cloud Architecture + Security + IAM + Networking + High Availability + Disaster Recovery + Monitoring + Cost Optimization + DevOps**

---

⭐ **Day 49 Complete — Cloud Security Architecture & Zero Trust**
