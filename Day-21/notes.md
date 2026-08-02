#  Day 21 – Cloud Auto Scaling

###  Introduction

Auto Scaling is a cloud computing feature that automatically increases or decreases computing resources based on the workload or demand of an application.

It helps applications maintain good performance during high traffic while reducing costs during low traffic.

---

## 1. What is Auto Scaling?

Auto Scaling automatically adjusts the number or capacity of cloud resources according to application requirements.

Example

Suppose an application normally requires 2 servers.

During a sale, traffic increases significantly:

Normal Traffic
2 Servers
    ↓
Traffic Increases
    ↓
Auto Scaling
    ↓
5 Servers

When traffic decreases, unnecessary servers can be removed automatically.

---

## 2. Why is Auto Scaling Important?

Auto Scaling helps organizations:

- Handle sudden traffic increases
- Maintain application performance
- Improve availability
- Reduce infrastructure costs
- Automatically manage resources
- Avoid over-provisioning
- Handle changing workloads efficiently

---

## 3. Types of Scaling

🔹 Horizontal Scaling

Horizontal scaling means adding or removing instances/servers.

Example:

2 Servers → 5 Servers

It is commonly used in cloud environments.

🔹 Vertical Scaling

Vertical scaling means increasing or decreasing the resources of an existing server.

Example:

4 GB RAM → 8 GB RAM
2 CPU → 4 CPU

Difference

Horizontal Scaling| Vertical Scaling
Adds/removes instances| Increases/decreases resources
Scale out / Scale in| Scale up / Scale down
Good for distributed systems| Useful for resource-heavy applications
Multiple servers| Usually one larger server

---

## 4. Important Auto Scaling Concepts

Minimum Capacity

The minimum number of instances that should be running.

Example:

Minimum = 2

The Auto Scaling system should generally maintain at least 2 instances.

Maximum Capacity

The maximum number of instances that can be created.

Example:

Maximum = 10

This prevents unlimited resource creation and unexpected costs.

Desired Capacity

The preferred number of instances under normal conditions.

Example:

Minimum = 2
Desired = 3
Maximum = 10

---

## 5. Scaling Policies

A scaling policy defines when and how resources should be added or removed.

🎯 Target Tracking

Resources are adjusted to maintain a target metric.

Example:

Target CPU Utilization = 50%

If CPU usage continuously goes above the target, more instances may be launched.

---

📈 Step Scaling

Different scaling actions can be taken depending on how much a metric changes.

Example:

CPU 50–70%  → Add 1 instance
CPU 70–90%  → Add 2 instances
CPU > 90%   → Add 3 instances

---

🗓️ Scheduled Scaling

Resources are scaled according to a predefined schedule.

Example:

9 AM → Increase instances
6 PM → Reduce instances

This is useful when traffic patterns are predictable.

---

## 6. Health Checks

Auto Scaling systems can use health checks to identify unhealthy instances.

Example:

Instance becomes unhealthy
        ↓
Health Check detects problem
        ↓
Unhealthy instance removed
        ↓
New instance launched

This improves application availability.

---

## 7. Auto Scaling and Load Balancing

Auto Scaling and Load Balancing are often used together.

Architecture

             Users
               ↓
        Load Balancer
               ↓
       Auto Scaling Group
          ↙    ↓    ↘
      EC2     EC2     EC2
    Instance Instance Instance

The Load Balancer distributes incoming traffic among available instances.

The Auto Scaling Group adjusts the number of instances based on demand.

---

## 8. AWS EC2 Auto Scaling

AWS provides Amazon EC2 Auto Scaling to automatically maintain the required number of EC2 instances.

Important concepts include:

- Auto Scaling Group
- Minimum capacity
- Desired capacity
- Maximum capacity
- Scaling policies
- Health checks
- Launch templates
- CloudWatch metrics

Example

Minimum Capacity = 2
Desired Capacity = 2
Maximum Capacity = 6

High Traffic
     ↓
CPU Usage Increases
     ↓
Scaling Policy Triggered
     ↓
New EC2 Instances Launched
     ↓
Traffic Distributed

When demand decreases, instances can be terminated according to the scaling policy.

---

## 9. Benefits of Auto Scaling

⚡ Performance

Automatically provides additional resources when workload increases.

💰 Cost Optimization

Resources can be reduced when demand decreases.

🛡️ Availability

Helps maintain sufficient healthy instances.

📈 Scalability

Applications can handle changing workloads.

🔄 Automation

Reduces the need for manual resource management.

---

## 10. Real-World Example

Consider an e-commerce website.

During normal hours:

Traffic → Low
Instances → 2

During a festival sale:

Traffic → Very High
Instances → Automatically increase

After the sale:

Traffic → Decreases
Instances → Automatically decrease

This allows the company to handle high traffic without permanently running a large number of servers.

---

## 11. Auto Scaling vs Load Balancing

Auto Scaling                | Load Balancing
Adjusts number of resources | Distributes traffic
Adds/removes instances      | Routes requests
Focuses on capacity         | Focuses on traffic distribution
Helps scalability           | Helps availability and performance

They work especially well together.

---

## 12. Key Takeaways

- Auto Scaling automatically adjusts cloud resources.
- Horizontal scaling adds or removes instances.
- Vertical scaling changes the capacity of an existing instance.
- Minimum, desired, and maximum capacity control scaling limits.
- Scaling policies determine when scaling occurs.
- Health checks help replace unhealthy instances.
- Load Balancing distributes traffic among instances.
- AWS EC2 Auto Scaling helps applications handle changing workloads automatically.
- Auto Scaling can improve both performance and cost efficiency.

---


**Next Goal**: Continue learning advanced cloud architecture and services.
