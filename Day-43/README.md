#  Day 43 – Cloud Security Architecture & Zero Trust

##  Overview

Day 43 focuses on **Cloud Security Architecture and Zero Trust**, covering the principles and technologies used to protect cloud applications, infrastructure, networks, identities, and data.

##  Topics Covered

- Cloud Security Architecture
- Defense in Depth
- Zero Trust Architecture
- Principle of Least Privilege
- Cloud Network Security
- WAF and Firewalls
- Encryption at Rest
- Encryption in Transit
- Key Management
- Security Monitoring
- Incident Response
- Shared Responsibility Model

##  Zero Trust

Zero Trust follows the principle:

> **Never Trust, Always Verify**

Every access request is authenticated, authorized, and continuously evaluated.

##  Security Architecture

```text
Internet
   ↓
WAF / DDoS Protection
   ↓
Load Balancer
   ↓
Application
   ↓
Private Database
   ↓
Encrypted Storage

IAM + MFA + Monitoring
        ↓
All Resources

## Key Learnings
- Use least-privilege permissions.
- Never expose sensitive resources unnecessarily.
- Encrypt data at rest and in transit.
- Use MFA for important accounts.
- Monitor cloud activity and security events.
- Apply multiple security layers.
- Follow Zero Trust principles.
- Understand the Shared Responsibility Model.

## Practical Goal

Design a secure cloud architecture for a Python/Flask AI application using:

WAF → Load Balancer → Application → Private Database + IAM + Encryption + Monitoring
