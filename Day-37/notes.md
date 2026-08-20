# Day 37: Cloud Disaster Recovery & Business Continuity

## 1. Introduction

In cloud computing, applications and services must remain available even when unexpected failures occur.

Failures can happen because of:

* Hardware failures
* Software failures
* Network outages
* Cyberattacks
* Human errors
* Natural disasters
* Data corruption
* Power failures
* Cloud service outages

**Disaster Recovery (DR)** is the process of restoring applications, systems, and data after a disruptive event.

**Business Continuity (BC)** is the broader strategy of ensuring that critical business operations can continue during and after a disruption.

---

# 2. What is Disaster Recovery?

Disaster Recovery is a set of processes, technologies, and strategies used to recover IT infrastructure, applications, and data after a disaster.

### Main objectives

* Minimize downtime
* Prevent permanent data loss
* Restore critical applications
* Maintain business operations
* Reduce financial losses
* Protect business-critical data

### Basic DR process

```text
Disaster Occurs
       ↓
Detect Failure
       ↓
Assess Impact
       ↓
Activate DR Plan
       ↓
Recover Infrastructure
       ↓
Restore Data
       ↓
Redirect Traffic
       ↓
Verify Applications
       ↓
Resume Normal Operations
```

---

# 3. What is Business Continuity?

Business Continuity refers to the ability of an organization to continue critical operations during and after a disruption.

Business continuity is broader than disaster recovery.

```text
Business Continuity
        |
        ├── Disaster Recovery
        ├── Data Protection
        ├── Backup Strategy
        ├── Communication Plan
        ├── Emergency Procedures
        └── Operational Recovery
```

### Example

If an organization's primary data center becomes unavailable:

* Employees need alternative communication methods.
* Customers should still be able to access important services.
* Applications should be recovered.
* Databases should be restored or replicated.
* Business operations should continue.

---

# 4. Disaster vs Disruption

A **disruption** is an event that interrupts normal operations.

A **disaster** is a major disruption that significantly affects systems, applications, data, or business operations.

### Examples

| Event               | Possible Impact              |
| ------------------- | ---------------------------- |
| Server failure      | Application unavailable      |
| Database corruption | Data unavailable             |
| Network failure     | Users cannot access services |
| Cyberattack         | Systems compromised          |
| Natural disaster    | Data center unavailable      |
| Human error         | Data deleted                 |
| Cloud outage        | Services unavailable         |

---

# 5. Disaster Recovery vs Business Continuity

| Feature      | Disaster Recovery                  | Business Continuity             |
| ------------ | ---------------------------------- | ------------------------------- |
| Focus        | IT recovery                        | Entire business                 |
| Main Goal    | Restore systems                    | Continue operations             |
| Scope        | Infrastructure, applications, data | People, processes, technology   |
| Example      | Restore database                   | Keep customer support operating |
| Relationship | Part of BC                         | Broader strategy                |

---

# 6. Why Disaster Recovery is Important

Disaster recovery is important because organizations depend heavily on digital infrastructure.

Without proper DR:

* Applications may remain unavailable.
* Important data may be permanently lost.
* Customers may be affected.
* Revenue may decrease.
* Reputation may be damaged.
* Regulatory requirements may not be met.

A well-designed DR strategy reduces these risks.

---

# 7. Recovery Time Objective (RTO)

**RTO** stands for **Recovery Time Objective**.

It defines the maximum acceptable amount of time that a system can remain unavailable after a disaster.

### Example

Suppose:

```text
RTO = 2 hours
```

This means the organization should recover the system within 2 hours.

### Lower RTO

Lower RTO generally requires:

* Faster recovery mechanisms
* More automation
* More infrastructure
* Higher cost

---

# 8. Recovery Point Objective (RPO)

**RPO** stands for **Recovery Point Objective**.

It defines the maximum acceptable amount of data loss measured in time.

### Example

Suppose:

```text
RPO = 15 minutes
```

This means the organization should be able to recover data to a point no more than approximately 15 minutes before the disruption.

### Lower RPO

A lower RPO generally requires:

* More frequent backups
* Continuous replication
* Additional infrastructure
* Higher cost

---

# 9. RTO vs RPO

| Concept | Meaning                      | Example    |
| ------- | ---------------------------- | ---------- |
| RTO     | Maximum acceptable downtime  | 2 hours    |
| RPO     | Maximum acceptable data loss | 15 minutes |

### Easy way to remember

**RTO → How quickly can we recover?**

**RPO → How much data can we afford to lose?**

---

# 10. Disaster Recovery Strategies

Cloud providers support multiple disaster recovery strategies.

The major approaches are:

1. Backup and Restore
2. Pilot Light
3. Warm Standby
4. Multi-Site / Hot Standby

---

# 11. Backup and Restore

This is one of the simplest DR approaches.

Data and system backups are stored separately and restored when required.

```text
Primary System
      |
      ↓
    Backup
      |
      ↓
Cloud Storage
      |
   Disaster
      ↓
Restore Data
      ↓
Recovery System
```

### Advantages

* Simple
* Lower cost
* Easy to understand
* Suitable for less critical applications

### Disadvantages

* Recovery can take longer
* Higher RTO
* Backups may become outdated
* Requires restoration process

---

# 12. Pilot Light

In a **Pilot Light** strategy, the minimum critical components are always running.

The remaining infrastructure is started when a disaster occurs.

```text
Primary Region
      |
      ↓
Database Replication
      |
      ↓
Secondary Region
      |
      └── Minimal Infrastructure
              ↓
         Disaster Occurs
              ↓
      Start Full Infrastructure
```

### Advantages

* Faster recovery than backup and restore
* Lower cost than a complete duplicate environment

### Disadvantages

* Requires automation
* Some components need to be started during recovery

---

# 13. Warm Standby

A warm standby environment contains a scaled-down but operational version of the production environment.

```text
Primary Environment
      |
      | Replication
      ↓
Warm Standby
      |
      ↓
Disaster
      |
      ↓
Scale Up
      |
      ↓
Production Recovery
```

### Advantages

* Faster recovery
* Easier failover
* Reduced downtime

### Disadvantages

* More expensive than pilot light
* Requires continuous maintenance

---

# 14. Multi-Site / Hot Standby

A hot standby architecture maintains a fully operational secondary environment.

Both environments can be ready to serve traffic.

```text
                 Users
                   |
              Load Balancer
                /       \
               /         \
        Region A        Region B
       Production      Standby
          |                |
       Database  ←→  Database
```

If one region fails, traffic can be redirected to the other region.

### Advantages

* Very low downtime
* Very fast recovery
* High availability

### Disadvantages

* Expensive
* Complex architecture
* Requires synchronization and monitoring

---

# 15. Comparing DR Strategies

| Strategy         | Cost        | Recovery Speed | Complexity  |
| ---------------- | ----------- | -------------- | ----------- |
| Backup & Restore | Low         | Slow           | Low         |
| Pilot Light      | Medium-Low  | Medium         | Medium      |
| Warm Standby     | Medium-High | Fast           | Medium-High |
| Multi-Site       | High        | Very Fast      | High        |

The appropriate strategy depends on business requirements.

---

# 16. High Availability vs Disaster Recovery

These concepts are related but different.

### High Availability

High Availability focuses on keeping services running continuously.

Example:

```text
Server A
   |
   ↓
If Server A fails
   |
   ↓
Server B handles traffic
```

### Disaster Recovery

Disaster Recovery focuses on recovering systems after a major disruption.

Example:

```text
Primary Region
      ↓
Major Failure
      ↓
Secondary Region
      ↓
Recovery
```

### Key Difference

**High Availability → Prevent or minimize downtime**

**Disaster Recovery → Recover after a major failure**

---

# 17. Fault Tolerance

Fault tolerance is the ability of a system to continue operating even when some components fail.

Example:

```text
Application
   |
   ├── Server 1
   ├── Server 2
   └── Server 3
```

If Server 1 fails, the remaining servers continue serving users.

Fault tolerance helps reduce the impact of individual component failures.

---

# 18. Backup and Restore

Backups are copies of data stored so that information can be recovered when the original data becomes unavailable or corrupted.

### Types of backups

#### Full Backup

Copies all selected data.

#### Incremental Backup

Copies data changed since the previous backup.

#### Differential Backup

Copies data changed since the last full backup.

---

# 19. Backup Best Practices

Important backup practices include:

* Automate backups
* Encrypt backup data
* Store backups separately
* Use multiple availability locations
* Test backups regularly
* Define retention policies
* Monitor backup failures
* Protect backups from accidental deletion

---

# 20. Cross-Region Disaster Recovery

Cloud providers allow organizations to replicate resources and data across different geographical regions.

Example:

```text
Region A
Primary Application
      |
      | Replication
      ↓
Region B
DR Environment
```

If Region A becomes unavailable, workloads can be recovered in Region B.

### Benefits

* Protection against regional failures
* Geographic redundancy
* Improved resilience
* Better business continuity

---

# 21. Failover

**Failover** is the process of moving operations from a failed primary system to a backup system.

```text
Primary System
      ↓
Failure
      ↓
Failover
      ↓
Secondary System
      ↓
Users continue accessing service
```

Failover can be:

* Manual
* Automated

Automated failover generally provides faster recovery.

---

# 22. Failback

**Failback** is the process of moving operations back to the original primary environment after it has been recovered.

```text
Primary Failure
      ↓
Failover
      ↓
DR Environment
      ↓
Primary Recovered
      ↓
Failback
      ↓
Primary Environment
```

---

# 23. Disaster Recovery Testing

A DR plan should not simply exist on paper.

It should be tested regularly.

### Common testing methods

#### Tabletop Exercise

Teams discuss how they would respond to a disaster.

#### Simulation

A controlled disaster scenario is created.

#### Failover Test

Traffic is intentionally moved to the backup environment.

#### Recovery Test

Systems and data are restored from backups.

---

# 24. Disaster Recovery Lifecycle

```text
Identify Risks
      ↓
Analyze Impact
      ↓
Define RTO/RPO
      ↓
Design DR Strategy
      ↓
Implement Solution
      ↓
Monitor
      ↓
Test
      ↓
Improve
```

---

# 25. Business Impact Analysis

A **Business Impact Analysis (BIA)** identifies how disruptions could affect business operations.

It helps determine:

* Critical applications
* Critical business processes
* Recovery priorities
* Financial impact
* Acceptable downtime
* Acceptable data loss

### Example

| Service          | Importance |     RTO |     RPO |
| ---------------- | ---------- | ------: | ------: |
| Payment System   | Critical   |  30 min |   5 min |
| Customer Portal  | High       |  1 hour |  15 min |
| Internal Reports | Medium     | 8 hours | 4 hours |

---

# 26. Risk Assessment

Risk assessment identifies possible threats and evaluates their impact.

### Example

```text
Threat
  ↓
Probability
  ↓
Potential Impact
  ↓
Risk Level
  ↓
Mitigation Strategy
```

Possible threats include:

* Hardware failure
* Cyberattack
* Data corruption
* Human error
* Natural disaster
* Network outage
* Service provider outage

---

# 27. Disaster Recovery in AWS

AWS provides multiple services that can support disaster recovery.

Examples include:

* Amazon S3
* Amazon EBS Snapshots
* Amazon RDS automated backups
* Amazon Aurora
* AWS Backup
* Amazon Route 53
* AWS Elastic Disaster Recovery
* AWS Elastic Load Balancing

These services can be combined to create DR architectures.

### Example

```text
Users
  ↓
Route 53
  ↓
Load Balancer
  ↓
Application
  ↓
Database
  ↓
Backups / Replication
  ↓
Secondary Region
```

---

# 28. Disaster Recovery in Microsoft Azure

Azure provides services for backup, replication, monitoring, and recovery.

Examples include:

* Azure Backup
* Azure Site Recovery
* Azure Storage
* Azure SQL Database
* Azure Traffic Manager
* Azure Load Balancer

Azure Site Recovery can help replicate and recover workloads in another location.

---

# 29. Disaster Recovery in Google Cloud

Google Cloud provides several services that can support resilient architectures.

Examples include:

* Cloud Storage
* Persistent Disk snapshots
* Cloud SQL backups
* Compute Engine
* Cloud Load Balancing
* Cloud DNS
* Backup and DR capabilities

These services can be combined to build resilient applications.

---

# 30. Cloud Disaster Recovery Architecture

A basic multi-region architecture can look like this:

```text
                       Users
                         |
                    DNS / Routing
                         |
             -------------------------
             |                       |
         Region A                Region B
         Primary                 DR Region
             |                       |
       Application              Application
             |                       |
         Database  ←------→     Replica
             |
          Backups
             |
       Cloud Storage
```

If Region A fails:

```text
Region A Failure
      ↓
Health Check
      ↓
Traffic Redirected
      ↓
Region B
      ↓
Application Continues
```

---

# 31. Disaster Recovery and Security

Security must also be considered in DR planning.

Important practices:

* Encrypt backups
* Use access control
* Protect backup accounts
* Enable logging
* Monitor recovery environments
* Use least privilege
* Protect backup credentials
* Test security controls
* Maintain audit trails

A backup is not useful if attackers can easily modify or delete it.

---

# 32. Immutable Backups

An immutable backup cannot be modified or deleted during a defined retention period.

This can help protect against:

* Ransomware
* Accidental deletion
* Malicious modification

```text
Production Data
      ↓
Backup
      ↓
Immutable Storage
      ↓
Protected Recovery Copy
```

---

# 33. Disaster Recovery Automation

Automation can significantly reduce recovery time.

Instead of manually recreating infrastructure, organizations can use:

* Infrastructure as Code
* Automated backups
* Automated replication
* Automated health checks
* Automated failover
* Automated deployment pipelines

Automation reduces human error and improves recovery speed.

---

# 34. Disaster Recovery with Infrastructure as Code

Infrastructure as Code tools can recreate infrastructure automatically.

Example:

```text
Infrastructure Code
       ↓
Cloud Resources
       ↓
Application Environment
       ↓
Recovery Environment
```

If infrastructure is lost, the environment can be recreated from code.

---

# 35. Common DR Mistakes

Avoid:

* Not having a DR plan
* Not defining RTO/RPO
* Keeping backups in only one location
* Never testing backups
* Relying entirely on manual recovery
* Ignoring security
* Not documenting recovery procedures
* Not updating the DR plan
* Assuming cloud automatically means disaster recovery

### Important

**Using the cloud does not automatically provide disaster recovery.**

A proper DR architecture must be designed and tested.

---

# 36. Disaster Recovery Best Practices

1. Identify critical workloads.
2. Perform a risk assessment.
3. Conduct a Business Impact Analysis.
4. Define RTO and RPO.
5. Automate backups.
6. Use geographic redundancy where required.
7. Protect backups.
8. Automate recovery where possible.
9. Test DR regularly.
10. Document recovery procedures.
11. Monitor the DR environment.
12. Continuously improve the DR strategy.

---

# 37. Real-World Example

Consider an online shopping application.

It contains:

```text
Web Application
      ↓
API Servers
      ↓
Database
      ↓
Payment System
```

Suppose the primary cloud region becomes unavailable.

A DR architecture could use:

```text
Users
  ↓
Global DNS / Traffic Routing
  ↓
Primary Region
  ↓
Application
  ↓
Database
  ↕
Database Replication
  ↕
DR Region
```

When the primary region fails:

```text
Primary Region
      ↓
Failure Detected
      ↓
Traffic Redirected
      ↓
DR Region
      ↓
Application Continues
```

This minimizes downtime and helps maintain business operations.

---

# 38. Key Terms

| Term              | Meaning                                         |
| ----------------- | ----------------------------------------------- |
| DR                | Disaster Recovery                               |
| BC                | Business Continuity                             |
| RTO               | Recovery Time Objective                         |
| RPO               | Recovery Point Objective                        |
| BIA               | Business Impact Analysis                        |
| Failover          | Switching to backup environment                 |
| Failback          | Returning to primary environment                |
| Backup            | Copy of data                                    |
| Replication       | Copying data between systems                    |
| Fault Tolerance   | Continuing operation despite component failures |
| High Availability | Keeping services available                      |
| Pilot Light       | Minimal recovery environment                    |
| Warm Standby      | Partially operational recovery environment      |
| Hot Standby       | Fully operational recovery environment          |

---

# 39. Day 37 Summary

Today I learned:

* Disaster Recovery
* Business Continuity
* RTO
* RPO
* Backup and Restore
* Pilot Light
* Warm Standby
* Multi-Site / Hot Standby
* High Availability
* Fault Tolerance
* Cross-Region Recovery
* Failover
* Failback
* Disaster Recovery Testing
* Business Impact Analysis
* Risk Assessment
* Cloud DR services
* DR automation
* Immutable backups
* DR best practices

---

# 40. Final Takeaway

Disaster Recovery is an essential part of cloud architecture.

A good DR strategy ensures that applications and data can be recovered when unexpected failures occur.

The most important concepts to remember are:

```text
RTO → How quickly should we recover?

RPO → How much data can we afford to lose?

Backup → How do we recover data?

Replication → How do we maintain another copy?

Failover → How do we switch to the backup?

Failback → How do we return to the primary?

Testing → Does our recovery plan actually work?
```

**Day 37 completed: Cloud Disaster Recovery & Business Continuity**
