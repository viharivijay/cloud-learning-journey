#  Cloud Security Architecture & Zero Trust

> **Cloud Learning Journey | Day 49 of 50**

##  Overview

Day 49 focuses on **Cloud Security Architecture and Zero Trust**, covering the principles and practices used to secure cloud applications, infrastructure, identities, networks, and data.

The goal is to understand how modern cloud environments implement **least privilege, identity-based security, encryption, network protection, monitoring, and automated security responses**.

---

##  Topics Covered

*  Cloud Shared Responsibility Model
*  Zero Trust Architecture
*  Identity and Access Management (IAM)
*  Authentication & Authorization
*  Multi-Factor Authentication (MFA)
*  Principle of Least Privilege
*  Cloud Network Security
*  Web Application Firewall (WAF)
*  Data Encryption
*  Secrets Management
*  Security Monitoring
*  Security Automation
*  DevSecOps

---

##  Zero Trust Model

```text
User / Device
      ↓
Verify Identity
      ↓
Check Context & Risk
      ↓
Authorize Request
      ↓
 Allow / Deny
```

### Core Principles

* **Verify explicitly**
* **Use least privilege**
* **Assume breach**

---

##  Secure Cloud Architecture

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
                Application Layer
                       │
                       ▼
                 Private Network
                       │
                       ▼
                   Database
                       │
                       ▼
              Encrypted Storage
```

Security controls are applied across identity, network, application, and data layers.

---

##  Key Learnings

| Concept            | Key Learning                              |
| ------------------ | ----------------------------------------- |
| IAM                | Controls identities and permissions       |
| Zero Trust         | Never trust, always verify                |
| MFA                | Adds additional authentication protection |
| Least Privilege    | Provides only required permissions        |
| WAF                | Protects web applications                 |
| Encryption         | Protects data at rest and in transit      |
| Secrets Management | Securely stores credentials               |
| Monitoring         | Detects suspicious activity               |
| DevSecOps          | Integrates security into development      |

---

##  Interview Takeaway

> **Modern cloud security is not based on trusting a network. It is based on continuously verifying identities, enforcing least privilege, protecting data, monitoring activity, and assuming that a breach could occur.**

---

##  Progress

**Cloud Learning Journey: 49/50 Days Completed**

```text
█████████████████████████████████████████████████░ 98%
```

###  Next: Day 50

**Final Cloud Capstone Project**

Combining:

`Cloud Architecture` + `Security` + `IAM` + `Networking` + `HA` + `DR` + `Monitoring` + `Cost Optimization` + `DevOps`

---

⭐ **Day 49 Complete — Cloud Security Architecture & Zero Trust**
