  # Cloud Security & IAM

##  Overview

Cloud Security is the practice of protecting cloud infrastructure, applications, data, networks, identities, and services from unauthorized access, attacks, data loss, and security threats.

**IAM (Identity and Access Management)** is a key part of cloud security that controls:

* Who can access cloud resources
* What resources they can access
* What actions they can perform

---

##  Learning Objectives

By the end of Day 28, you should understand:

* Cloud Security fundamentals
* CIA Triad
* Shared Responsibility Model
* Identity and Access Management (IAM)
* Authentication vs Authorization
* IAM Users, Groups, Roles, and Policies
* Principle of Least Privilege
* Multi-Factor Authentication (MFA)
* Role-Based Access Control (RBAC)
* Access Keys and credentials
* Common cloud security threats
* Cloud security best practices

---

# 1. What is Cloud Security?

Cloud Security refers to the technologies, policies, processes, and practices used to protect cloud-based resources.

### Cloud Security protects:

* Data
* Applications
* Virtual machines
* Containers
* Networks
* Databases
* APIs
* User identities
* Cloud infrastructure

### Main objectives

1. Confidentiality
2. Integrity
3. Availability

---

# 2. CIA Triad

The CIA Triad represents the three fundamental goals of information security.

## Confidentiality

Ensures that only authorized users can access information.

**Example:**
A database containing customer information should only be accessible to authorized employees.

## Integrity

Ensures that data is accurate and cannot be modified without authorization.

**Example:**
An attacker should not be able to modify transaction records.

## Availability

Ensures that systems and data remain accessible when needed.

**Example:**
A web application should remain available to users even during high traffic.

```text
                 CIA TRIAD
                    |
        ---------------------------
        |            |            |
 Confidentiality  Integrity  Availability
```

---

# 3. Shared Responsibility Model

Cloud security is a shared responsibility between the cloud provider and the customer.

## Cloud Provider Responsibility

The provider generally protects the infrastructure **of the cloud**.

Examples:

* Physical data centers
* Physical servers
* Hardware
* Core networking
* Physical security
* Underlying cloud infrastructure

## Customer Responsibility

The customer protects what they deploy and configure **in the cloud**.

Examples:

* User accounts
* IAM permissions
* Applications
* Data
* Operating system configuration
* Network rules
* Security configurations
* Encryption settings

```text
          CLOUD SECURITY
                |
       -------------------
       |                 |
 Cloud Provider       Customer
       |                 |
 Infrastructure       Data
 Hardware             IAM
 Data Centers         Applications
 Networking           OS Configuration
 Physical Security   Network Rules
```

### Key Point

> The cloud provider secures the infrastructure, while the customer is responsible for securing their resources, identities, data, and configurations.

---

# 4. Identity and Access Management (IAM)

IAM is used to manage identities and permissions in a cloud environment.

IAM answers two important questions:

```text
Who are you?
     ↓
Authentication

What are you allowed to do?
     ↓
Authorization
```

IAM helps organizations:

* Manage users
* Manage permissions
* Control access
* Enforce security policies
* Apply least privilege
* Monitor access

---

# 5. Authentication

Authentication verifies the identity of a user or service.

### Examples

* Username and password
* OTP
* MFA
* Security keys
* Biometrics
* Access credentials

```text
User
  ↓
Credentials
  ↓
Authentication
  ↓
Identity Verified
```

### Remember

> Authentication = Who are you?

---

# 6. Authorization

Authorization determines what an authenticated user or service is allowed to do.

Example:

```text
User
 ↓
Authenticated
 ↓
Authorization
 ↓
Read S3 Bucket
```

The user may be allowed to read files but not delete them.

### Remember

> Authorization = What can you do?

---

# 7. Authentication vs Authorization

| Authentication         | Authorization                |
| ---------------------- | ---------------------------- |
| Verifies identity      | Determines permissions       |
| Happens first          | Happens after authentication |
| Answers "Who are you?" | Answers "What can you do?"   |
| Password, MFA, OTP     | Policies, roles, permissions |

---

# 8. IAM Users

An IAM user represents an identity that can access cloud resources.

Example:

```text
Company
   |
   ├── Developer
   ├── Tester
   ├── Analyst
   └── Administrator
```

Different users can have different permissions.

Example:

```text
Developer → Development resources
Tester    → Testing resources
Analyst   → Read-only data
Admin     → Administrative resources
```

---

# 9. IAM Groups

An IAM group is a collection of users.

Instead of assigning permissions individually:

```text
Developer 1 → Permissions
Developer 2 → Permissions
Developer 3 → Permissions
```

Create a group:

```text
Developer Group
      |
      ├── Developer 1
      ├── Developer 2
      └── Developer 3
```

Permissions can then be assigned to the group.

### Benefits

* Easier permission management
* Consistent access control
* Easier onboarding/offboarding
* Reduced administrative work

---

# 10. IAM Roles

An IAM role provides permissions that can be assumed by users or cloud services.

Roles are especially useful for applications and cloud services.

Example:

```text
EC2 Instance
     |
     ↓
  IAM Role
     |
     ↓
S3 Read Permission
```

The application can access the required resource without storing permanent credentials directly in the application.

### Benefits

* Improved security
* Reduced credential exposure
* Temporary access
* Useful for cloud services
* Supports least privilege

---

# 11. IAM Policies

A policy defines what actions are allowed or denied.

A simplified policy can be represented as:

```text
Effect: Allow
Action: Read
Resource: Specific Storage Bucket
```

A policy generally answers:

* What action?
* On which resource?
* Is the action allowed or denied?

Example:

```text
User
  ↓
Policy
  ↓
Allow → Read
  ↓
Specific Storage Resource
```

---

# 12. Principle of Least Privilege

The Principle of Least Privilege means:

> Give a user, application, or service only the permissions required to perform its job.

###  Bad approach

```text
Developer
   ↓
Administrator Access
```

If the developer only needs to read application logs, administrator access is unnecessary.

###  Better approach

```text
Developer
   ↓
Read-Only Log Access
```

### Benefits

* Reduces attack surface
* Limits damage from compromised accounts
* Improves security
* Makes permission management easier

---

# 13. Multi-Factor Authentication (MFA)

MFA adds an additional authentication factor.

Without MFA:

```text
Password
   ↓
Login
```

With MFA:

```text
Password
   +
Authentication Code / Security Key
   ↓
Login
```

### Benefits

* Protects against stolen passwords
* Adds an additional security layer
* Reduces unauthorized access

---

# 14. Access Keys and Credentials

Cloud platforms provide credentials for programmatic access.

Applications can use credentials to communicate with cloud APIs.

```text
Application
     ↓
Credentials
     ↓
Cloud API
     ↓
Cloud Resource
```

### Security Rules

Never:

* Hard-code credentials into source code
* Commit credentials to GitHub
* Share credentials publicly
* Store credentials in plain-text files
* Upload credentials to public repositories

Instead, use:

* IAM roles
* Secret management systems
* Environment-specific configuration
* Temporary credentials

---

# 15. Role-Based Access Control (RBAC)

RBAC assigns permissions according to a user's role.

Example:

```text
                 Organization
                      |
          -------------------------
          |           |           |
      Developer     Tester      Admin
          |           |           |
       Code         Test       Admin
       Access       Access     Access
```

### Advantages

* Simplifies permission management
* Improves security
* Reduces excessive permissions
* Makes access easier to audit

---

# 16. Common Cloud Security Threats

## 1. Misconfigured Storage

A private storage bucket may accidentally become publicly accessible.

## 2. Weak Passwords

Weak passwords can be compromised through attacks such as credential guessing.

## 3. No MFA

A compromised password can become more dangerous when MFA is not enabled.

## 4. Excessive Permissions

Giving users unnecessary administrator privileges increases security risk.

## 5. Exposed Access Keys

Credentials accidentally uploaded to GitHub can be discovered and abused.

## 6. Unpatched Systems

Outdated operating systems and software may contain known vulnerabilities.

## 7. Insecure APIs

Poorly protected APIs can expose sensitive cloud resources.

## 8. Poor Network Configuration

Unnecessary public access or open ports can increase the attack surface.

---

# 17. Cloud Security Best Practices

### Identity Security

* Enable MFA
* Use strong authentication
* Avoid shared accounts
* Regularly review user accounts

### Permission Management

* Follow least privilege
* Use IAM roles
* Avoid unnecessary administrator access
* Review permissions regularly

### Credential Security

* Never hard-code credentials
* Rotate credentials when necessary
* Use secret management
* Prefer temporary credentials

### Data Security

* Encrypt sensitive data
* Use secure backups
* Restrict storage access
* Protect sensitive information

### Network Security

* Use firewalls
* Restrict unnecessary ports
* Limit public access
* Segment networks where appropriate

### Monitoring

* Monitor authentication events
* Monitor API activity
* Maintain audit logs
* Investigate suspicious activity

---

# 18. IAM Architecture

```text
                    CLOUD ACCOUNT
                         |
                        IAM
                         |
        ---------------------------------
        |               |               |
      Users           Groups          Roles
        |               |               |
        ----------- Policies ------------
                         |
                    Permissions
                         |
        ---------------------------------
        |               |               |
       EC2             Storage        Database
```

---

# 19. Practical Lab

## Lab 1 — Create a Test User

Create a test user in your cloud platform.

Understand:

* User identity
* Authentication
* Permissions

## Lab 2 — Create a Group

Create:

```text
Developers
```

Add the test user to the group.

## Lab 3 — Assign Limited Permissions

Give the group read-only permissions for a test resource.

## Lab 4 — Explore IAM Roles

Create or inspect a role that can be used by a cloud service.

## Lab 5 — Enable MFA

Explore MFA configuration for the account.

## Lab 6 — Review Permissions

Check whether each user has only the permissions they actually need.

---

# 20. Interview Questions

### Q1. What is IAM?

IAM stands for Identity and Access Management. It controls identities and permissions for accessing cloud resources.

### Q2. What is authentication?

Authentication verifies the identity of a user or service.

### Q3. What is authorization?

Authorization determines which resources and actions an authenticated identity is allowed to access.

### Q4. What is the Principle of Least Privilege?

It means giving users and services only the minimum permissions required to perform their tasks.

### Q5. What is an IAM role?

An IAM role provides permissions that can be assumed by users or cloud services, often avoiding the need for permanent credentials.

### Q6. Why is MFA important?

MFA provides an additional authentication factor and helps protect accounts even when passwords are compromised.

### Q7. What is RBAC?

RBAC stands for Role-Based Access Control. It assigns permissions according to predefined roles.

### Q8. What is the Shared Responsibility Model?

It defines how security responsibilities are divided between the cloud provider and the customer.

### Q9. Why should credentials not be stored in GitHub?

Exposed credentials can be stolen and used to access cloud resources, potentially resulting in data loss or unexpected costs.

### Q10. What are the main goals of cloud security?

The primary goals are confidentiality, integrity, and availability.

---

# 21. Key Takeaways

* Cloud security protects cloud resources and data.
* IAM controls identities and permissions.
* Authentication verifies identity.
* Authorization determines permissions.
* Users represent identities.
* Groups organize users.
* Roles provide permissions that can be assumed.
* Policies define allowed or denied actions.
* Least privilege reduces security risks.
* MFA provides an additional layer of protection.
* RBAC simplifies access management.
* Credentials must never be exposed publicly.
* Security is a shared responsibility between the provider and customer.

---

#  Day 28 Quick Revision

```text
Cloud Security
      ↓
CIA Triad
      ↓
Shared Responsibility
      ↓
IAM
      ↓
Authentication + Authorization
      ↓
Users + Groups + Roles
      ↓
Policies
      ↓
Least Privilege
      ↓
MFA
      ↓
RBAC
      ↓
Security Best Practices
```

---

##  Day 28 Keywords

`Cloud Security`
`IAM`
`Authentication`
`Authorization`
`IAM User`
`IAM Group`
`IAM Role`
`IAM Policy`
`Least Privilege`
`MFA`
`RBAC`
`Cloud Credentials`
`Shared Responsibility Model`
`CIA Triad`
