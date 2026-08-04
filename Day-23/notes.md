# Day 23 — Cloud Disaster Recovery & Business Continuity

## 1. Disaster Recovery (DR)

Disaster Recovery is the process of restoring applications, infrastructure, and data after a disaster or major failure.

A disaster can include:

Hardware failure
Software failure
Cyberattacks
Accidental data deletion
Natural disasters
Power or network failures
Cloud service outages

### Goal: Minimize downtime and data loss.

## 2. Business Continuity (BC)

Business Continuity is the ability of an organization to continue its critical business operations during and after a disruption.

Example:
If an e-commerce website's primary server goes down, a backup system can keep the website running so customers can continue placing orders.

DR vs Business Continuity
Disaster Recovery	Business Continuity
Focuses on recovering IT systems	Focuses on continuing business operations
Restores applications and data	Keeps critical services operating
Part of business continuity planning	Broader strategy

## 3. RPO – Recovery Point Objective

RPO defines the maximum acceptable amount of data loss measured in time.

Example:

If the RPO is 1 hour, the organization should be able to recover data from within the last hour.

Lower RPO → Less data loss

## 4. RTO – Recovery Time Objective

RTO defines the maximum acceptable time required to restore a system after failure.

Example:

If RTO = 30 minutes, the application should be restored within 30 minutes.

Lower RTO → Faster recovery

RPO vs RTO
RPO	RTO
Measures acceptable data loss	Measures acceptable downtime
Focuses on data	Focuses on recovery time
Example: 1 hour	Example: 30 minutes

Easy way to remember:

RPO = How much data can we afford to lose?
RTO = How much time can we afford to be down?

## 5. Backup and Restore

A backup is a copy of important data stored separately so it can be recovered later.

Common backup approaches:

Full backup
Incremental backup
Differential backup
Automated cloud backups
Database backups
Snapshot-based backups

Backup → Store → Recover

## 6. Disaster Recovery Strategies

1. Backup and Restore

Data is backed up and restored when required.

Cost: Low
Recovery: Slow

Suitable for less critical applications.

2. Pilot Light

A minimal version of the infrastructure is always running.

When a disaster occurs, additional resources are started.

Cost: Medium
Recovery: Faster than backup/restore

3. Warm Standby

A smaller but functional version of the production environment is continuously running.

During failure, it can be scaled up.

Cost: Medium–High
Recovery: Fast

4. Hot Standby / Active-Active

Two complete environments operate simultaneously.

If one environment fails, traffic can be redirected to the other.

Cost: High
Recovery: Very fast

## 7. High Availability vs Disaster Recovery

These concepts are related but different.

High Availability (HA):

Prevents or minimizes service interruption.
Uses redundancy and failover.
Designed for continuous operation.

Disaster Recovery (DR):

Focuses on recovering after a major failure.
Uses backups, replication, and recovery environments.
Designed for larger disruptions.

Example:

A server fails → High Availability moves traffic to another server.

A whole region becomes unavailable → Disaster Recovery restores services in another region.

## 8. Cloud Disaster Recovery Architecture

A typical cloud DR setup can look like:

Users → Load Balancer → Primary Application → Primary Database

At the same time:

Primary Database → Replication/Backup → DR Environment

If the primary environment fails:

Users → DR Environment → Backup/Replica Database

This allows applications and data to be recovered with minimal downtime.

## 9. AWS Disaster Recovery Services

AWS provides several services that can support disaster recovery, including:

Amazon S3 – Data storage and backup
Amazon EC2 – Compute resources for recovery
Amazon RDS – Managed databases and backups
AWS Backup – Centralized backup management
AWS Elastic Disaster Recovery – Disaster recovery for applications

## 10. Azure Disaster Recovery Services

Microsoft Azure provides:

Azure Backup – Backup and recovery
Azure Site Recovery – Replication and disaster recovery
Azure Storage – Durable data storage
Azure SQL Database – Database backup and recovery capabilities

## 11. Why Cloud is Useful for Disaster Recovery

Cloud platforms make DR easier because organizations can use:

Multiple availability zones
Multiple regions
Automated backups
Data replication
Infrastructure as Code
Auto scaling
Load balancing
Monitoring and alerts

### Benefits

✅ Reduced downtime
✅ Reduced data loss
✅ Better availability
✅ Automated recovery
✅ Flexible infrastructure
✅ Geographic redundancy
✅ Cost-effective compared with maintaining a second physical data center

## 12. Real-World Example

Imagine an online shopping company stores its application in Region A.

Suddenly, Region A experiences a major outage.

The company has:

Database backups
Replicated data
A DR environment in Region B
DNS/failover configuration
Monitoring and alerts

When Region A fails:

Region A fails → Failover → Region B becomes active → Users continue accessing the application

This is cloud-based disaster recovery.

## Day 23 Quick Revision


DR → Recover systems after disaster
BC → Keep business running
RPO → Acceptable data loss
RTO → Acceptable downtime
Backup → Copy of data
Replication → Copy data continuously/regularly
Failover → Switch to backup system
HA → Minimize service interruption
DR → Recover after major disruption
