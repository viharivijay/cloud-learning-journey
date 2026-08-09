#  Day 28 — Cloud Security & IAM

##  Overview

Day 28 focuses on **Cloud Security and Identity & Access Management (IAM)**.

Cloud security protects cloud infrastructure, applications, data, networks, and identities from unauthorized access and security threats.

IAM controls **who can access cloud resources and what actions they are allowed to perform**.

---

##  Learning Objectives

By completing Day 28, I learned:

*  Cloud Security fundamentals
*  CIA Triad
*  Shared Responsibility Model
*  Identity and Access Management (IAM)
*  Authentication
*  Authorization
*  IAM Users and Groups
*  IAM Roles
*  IAM Policies
*  Principle of Least Privilege
*  Multi-Factor Authentication (MFA)
*  Role-Based Access Control (RBAC)
*  Access Keys and credential security
*  Common cloud security threats
*  Cloud security best practices

---

##  Topics Covered

### 1. Cloud Security

Understanding how cloud environments are protected from unauthorized access, attacks, data loss, and other security risks.

### 2. CIA Triad

| Principle       | Meaning                                                            |
| --------------- | ------------------------------------------------------------------ |
| Confidentiality | Only authorized users can access data                              |
| Integrity       | Data remains accurate and protected from unauthorized modification |
| Availability    | Systems and data remain accessible when required                   |

### 3. Shared Responsibility Model

Understanding how security responsibilities are divided between:

* Cloud Provider
* Cloud Customer

### 4. IAM

IAM manages:

* Identities
* Permissions
* Access control
* Authentication
* Authorization

### 5. IAM Components

```text
IAM
├── Users
├── Groups
├── Roles
└── Policies
```

### 6. Authentication vs Authorization

```text
Authentication
      ↓
Who are you?

Authorization
      ↓
What can you do?
```

### 7. Least Privilege

Users and applications should receive only the permissions required to perform their tasks.

### 8. MFA

Multi-Factor Authentication adds an additional verification layer beyond a password.

### 9. RBAC

Role-Based Access Control assigns permissions based on predefined roles.

---

##  IAM Architecture

```text
                 CLOUD ACCOUNT
                       |
                      IAM
                       |
        --------------------------------
        |              |               |
      Users          Groups          Roles
        |              |               |
        ----------- Policies -----------
                       |
                  Permissions
                       |
        --------------------------------
        |              |               |
       EC2           Storage         Database
```

---

##  Practical Work

### IAM Practice

* [ ] Create a test IAM user
* [ ] Create an IAM group
* [ ] Add the user to the group
* [ ] Assign limited permissions
* [ ] Explore IAM roles
* [ ] Explore IAM policies
* [ ] Enable MFA
* [ ] Review permissions
* [ ] Verify least-privilege access

> Use a test/free-tier environment where possible and avoid creating unnecessary paid resources.

---

##  Security Best Practices

* Enable MFA
* Use strong authentication
* Follow least privilege
* Use IAM roles where appropriate
* Avoid hard-coded credentials
* Never commit secrets to GitHub
* Review permissions regularly
* Encrypt sensitive data
* Restrict unnecessary network access
* Monitor authentication and API activity
* Keep systems and software updated

---

##  Interview Preparation

### Important Questions

**1. What is IAM?**

IAM is a cloud security service/framework used to manage identities and control access to cloud resources.

**2. What is authentication?**

Authentication verifies the identity of a user or service.

**3. What is authorization?**

Authorization determines what an authenticated identity is allowed to access or perform.

**4. What is the Principle of Least Privilege?**

It means granting only the minimum permissions required to perform a task.

**5. What is an IAM role?**

An IAM role provides permissions that can be assumed by users or cloud services.

**6. What is MFA?**

MFA adds an additional authentication factor to improve account security.

**7. What is the Shared Responsibility Model?**

It defines the security responsibilities shared between the cloud provider and customer.

---

##  Key Takeaways

>  IAM is a fundamental component of cloud security.

>  Authentication answers **"Who are you?"**

>  Authorization answers **"What can you do?"**

>  Least privilege means **"Give only the access that is required."**

>  Cloud security is a **shared responsibility** between the provider and customer.

>  MFA adds an additional layer of protection.

>  Never expose cloud credentials or secrets in public repositories.

---

## Learning Progress

**Cloud Learning Journey — Day 28 / 50**


### Previous Topics

* Cloud Fundamentals
* Cloud Networking
* Virtualization
* Git & GitHub
* Linux
* Cloud Storage
* Cloud Databases
* Infrastructure as Code
* Terraform
* Ansible
* Load Balancing
* Auto Scaling
* Serverless Computing
* Disaster Recovery
* Cost Optimization
* Cloud Monitoring
* Docker
* Kubernetes

### Current Topic

**Day 28 → Cloud Security & IAM**

---

##  Next Step

After completing Day 28, continue to the next new cloud concept without repeating previously completed topics.

**Goal: Build practical cloud knowledge step-by-step and maintain a structured 50-day learning journey.**

---

**Day 28 Completed — Cloud Security & IAM**
