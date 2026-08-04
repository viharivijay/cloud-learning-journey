# ☁️ Day 23 – Cloud Disaster Recovery & Business Continuity

## 📌 Overview

Day 23 of my **Cloud Learning Journey** focused on **Cloud Disaster Recovery (DR) and Business Continuity (BC)**.

I learned how cloud platforms help organizations protect their applications and data, minimize downtime, and recover quickly from failures and disasters.

## 📚 Topics Covered

* Disaster Recovery (DR)
* Business Continuity (BC)
* Recovery Point Objective (RPO)
* Recovery Time Objective (RTO)
* Backup and Restore
* Disaster Recovery Strategies
* High Availability vs Disaster Recovery
* Cloud Disaster Recovery Architecture
* AWS Disaster Recovery Services
* Azure Disaster Recovery Services
* Failover and Replication

## 🔑 Key Concepts

### Disaster Recovery

Disaster Recovery is the process of restoring applications, infrastructure, and data after a major failure or disaster.

### Business Continuity

Business Continuity ensures that critical business operations can continue during and after disruptions.

### RPO – Recovery Point Objective

RPO defines the maximum acceptable amount of data loss measured in time.

**Example:** RPO = 1 hour means the organization can tolerate losing up to approximately one hour of data.

### RTO – Recovery Time Objective

RTO defines the maximum acceptable time required to restore a system.

**Example:** RTO = 30 minutes means the system should be restored within 30 minutes.

## 🔄 Disaster Recovery Strategies

| Strategy                    | Cost        | Recovery Speed |
| --------------------------- | ----------- | -------------- |
| Backup & Restore            | Low         | Slow           |
| Pilot Light                 | Medium      | Moderate       |
| Warm Standby                | Medium–High | Fast           |
| Hot Standby / Active-Active | High        | Very Fast      |

## ☁️ Cloud DR Services

### AWS

* Amazon S3
* Amazon EC2
* Amazon RDS
* AWS Backup
* AWS Elastic Disaster Recovery

### Microsoft Azure

* Azure Backup
* Azure Site Recovery
* Azure Storage
* Azure SQL Database

## ⚡ High Availability vs Disaster Recovery

**High Availability:** Minimizes service interruptions using redundancy and failover.

**Disaster Recovery:** Focuses on restoring systems after major failures or disasters.

## 🎯 Key Takeaways

* Disaster Recovery helps organizations recover from failures.
* Business Continuity helps keep critical operations running.
* RPO focuses on **data loss**.
* RTO focuses on **downtime**.
* Backups and replication are important parts of DR.
* Multiple regions and availability zones can improve resilience.
* Cloud platforms provide scalable and automated disaster recovery solutions.

## 📈 Learning Progress

**Day 23/30+ – Completed ✅**

Continuing my journey to build strong foundations in **Cloud Computing, AWS, Azure, DevOps, and Cloud Infrastructure**.
