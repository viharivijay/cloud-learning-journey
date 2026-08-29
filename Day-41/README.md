#  High Availability & Fault-Tolerant Architecture


##  Overview

**High Availability (HA)** and **Fault Tolerance (FT)** are cloud architecture principles used to build reliable systems that continue operating during infrastructure or service failures.

* **High Availability:** Minimizes downtime through redundancy and failover.
* **Fault Tolerance:** Allows systems to continue functioning despite component failures.

##  Topics Covered

* High Availability & Fault Tolerance
* Redundancy and Replication
* Load Balancing
* Health Checks
* Automatic Failover
* Availability Zones & Regions
* Active-Active & Active-Passive Architecture
* Database High Availability
* Disaster Recovery
* RTO & RPO
* Graceful Degradation
* Circuit Breaker Pattern
* Retry & Backoff
* Fault Isolation
* Monitoring & Observability
* Single Points of Failure

##  High Availability Architecture

```text
                    USERS
                      |
                      ↓
                Load Balancer
                 /          \
                ↓            ↓
             AZ-A           AZ-B
           App Server     App Server
                \            /
                 \          /
                  ↓        ↓
                Database
                 /    \
              Primary Replica
```

If one application instance or Availability Zone fails, traffic can be redirected to healthy resources.

##  Active-Active vs Active-Passive

| Active-Active                   | Active-Passive             |
| ------------------------------- | -------------------------- |
| Both environments serve traffic | One environment is standby |
| Faster failover                 | Failover required          |
| Better resource utilization     | Lower operating cost       |
| More complex                    | Simpler                    |
| Suitable for critical workloads | Common for DR              |

##  Disaster Recovery

Common strategies:

`Backup & Restore` → `Pilot Light` → `Warm Standby` → `Active-Active`

### RTO & RPO

* **RTO:** Maximum acceptable time to restore service.
* **RPO:** Maximum acceptable amount of data loss measured in time.

Example:

```text
RTO = 30 minutes
RPO = 5 minutes
```

##  Resilience Patterns

* **Load Balancing** → Distributes traffic across healthy resources.
* **Health Checks** → Detect unhealthy instances.
* **Circuit Breaker** → Prevents repeated calls to failing services.
* **Retry with Backoff** → Handles temporary failures.
* **Graceful Degradation** → Maintains essential functionality during partial failures.
* **Replication** → Maintains redundant copies of data.

## ☁️ Cloud Services

| AWS                    | Azure               | Google Cloud            |
| ---------------------- | ------------------- | ----------------------- |
| Elastic Load Balancing | Azure Load Balancer | Cloud Load Balancing    |
| Route 53               | Traffic Manager     | Cloud DNS               |
| EC2 Auto Scaling       | VM Scale Sets       | Managed Instance Groups |
| RDS Multi-AZ           | Availability Zones  | Regional Services       |
| AWS Backup             | Azure Backup        | Backup & DR             |

##  Best Practices

```text
☐ Eliminate Single Points of Failure
☐ Deploy across multiple Availability Zones
☐ Use Load Balancers and Health Checks
☐ Implement Automatic Failover
☐ Replicate critical data
☐ Define RTO and RPO
☐ Monitor system health
☐ Automate recovery processes
☐ Test Disaster Recovery regularly
☐ Design for graceful degradation
```

##  Key Takeaway

> **Reliable cloud systems are designed to expect failures rather than assume failures will never happen.**

High availability focuses on **minimizing downtime**, while fault tolerance focuses on **continuing operation despite failures**.

## Learning Outcome

After completing **Day 41**, I learned how to design resilient cloud architectures using **redundancy, load balancing, multi-AZ/multi-region deployment, replication, failover, disaster recovery, RTO/RPO, and resilience patterns**.

##  Tags

`#CloudComputing` `#HighAvailability` `#FaultTolerance` `#CloudArchitecture` `#DisasterRecovery` `#AWS` `#Azure` `#GCP` `#DevOps` `#CloudLearningJourney`
