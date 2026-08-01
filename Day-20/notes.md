# Cloud Monitoring & Observability

## 1. Introduction

Cloud Monitoring and Observability are important practices used to maintain the performance, availability, reliability, and security of cloud applications and infrastructure.

Cloud environments contain many resources such as virtual machines, databases, containers, networks, and applications. Monitoring helps us understand how these resources are performing and quickly identify problems.

---

## 2. What is Cloud Monitoring?

Cloud Monitoring is the process of continuously observing cloud resources and applications by collecting information such as:

- CPU usage
- Memory usage
- Disk usage
- Network traffic
- Application performance
- Error rates
- Response time
- Availability

Monitoring helps organizations detect failures, performance problems, and unusual behavior.

Example

If a virtual machine's CPU usage continuously reaches 90%, monitoring can detect it and generate an alert.

---

## 3. Why Cloud Monitoring is Important

Cloud monitoring helps to:

- Detect problems quickly
- Improve application performance
- Maintain high availability
- Reduce downtime
- Monitor resource utilization
- Control cloud costs
- Identify security issues
- Support troubleshooting
- Improve user experience

---

## 4. What is Observability?

Observability is the ability to understand the internal state and behavior of a system by analyzing the information it produces.

The three major pillars of observability are:

### 1. Metrics

Metrics are numerical measurements collected over time.

Examples:

- CPU utilization
- Memory usage
- Number of requests
- Error rate
- Response time

### 2. Logs

Logs are records of events that happen inside an application or system.

Example:

2026-08-01 10:30:15
User authentication successful

Logs are useful for troubleshooting and understanding what happened inside a system.

### 3. Traces

Traces show how a request travels through different components of a distributed application.

For example:

User Request
     ↓
Web Server
     ↓
API Service
     ↓
Database
     ↓
Response

Tracing helps identify which component is causing delays or failures.

---

## 5. Monitoring vs Observability

Monitoring                           | Observability
Tells us that something is wrong     | Helps us understand why it is wrong
Focuses mainly on known problems     | Helps investigate unknown problems
Uses metrics, alerts, and dashboards | Uses metrics, logs, and traces
Useful for detecting issues          | Useful for investigating issues

In simple terms:

Monitoring = What is happening?

Observability = Why is it happening?

---

## 6. Important Cloud Metrics

### CPU Utilization

Shows how much processing capacity is being used.

### Memory Utilization

Shows how much RAM is being consumed.

### Disk Utilization

Shows storage usage and disk activity.

### Network Traffic

Measures data moving into and out of cloud resources.

### Response Time

Measures how long an application takes to respond to requests.

### Error Rate

Shows how frequently application requests fail.

### Availability

Measures how often a service is operational and accessible.

---

## 7. Alerts

An alert is a notification generated when a predefined condition or threshold is reached.

Example:

CPU Usage > 80%
       ↓
Alert Triggered
       ↓
Notification Sent

Alerts can notify administrators through different channels depending on the cloud platform and configuration.

---

## 8. Dashboards

A monitoring dashboard provides a visual representation of system health and performance.

A dashboard may display:

- CPU utilization
- Memory usage
- Network traffic
- Request count
- Error rate
- Response time
- Service availability

Dashboards make it easier to understand the overall health of cloud infrastructure.

---

## 9. Azure Monitoring

Microsoft Azure provides several monitoring services.

Azure Monitor

Azure Monitor collects and analyzes monitoring data from Azure resources and applications.

It can be used to:

- Collect metrics
- Collect logs
- Create dashboards
- Configure alerts
- Analyze resource performance

Log Analytics

Log Analytics is used to query and analyze log data collected by Azure Monitor.

Application Insights

Application Insights helps monitor application performance and detect application-related issues.

It can help analyze:

- Requests
- Failures
- Dependencies
- Response times
- Application performance

---

## 10. AWS Monitoring

AWS provides Amazon CloudWatch for monitoring AWS resources and applications.

CloudWatch can be used for:

- Metrics
- Logs
- Alarms
- Dashboards
- Application monitoring
- Resource monitoring

Example:

EC2 Instance
     ↓
CloudWatch
     ↓
Metrics + Logs
     ↓
Alarm
     ↓
Notification

---

## 11. Monitoring Workflow

A typical cloud monitoring workflow looks like this:

Cloud Resources
      ↓
Data Collection
      ↓
Metrics + Logs + Traces
      ↓
Monitoring Platform
      ↓
Analysis
      ↓
Alert / Dashboard
      ↓
Action

---

## 12. Real-World Example

Suppose an online shopping application suddenly receives thousands of users.

The monitoring system detects:

CPU Usage      → 92%
Response Time  → High
Error Rate     → Increasing

An alert is triggered.

The cloud administrator investigates the logs and traces and identifies the problem.

The team can then take corrective action such as:

- Increasing resources
- Scaling the application
- Fixing application errors
- Optimizing database queries
- Restarting unhealthy services

---

## 13. Monitoring and Cost Optimization

Monitoring is also useful for controlling cloud costs.

For example, if a virtual machine is consistently using only 10% CPU, the organization may be paying for more computing capacity than necessary.

Monitoring can help identify:

- Underutilized resources
- Unused resources
- Excessive storage
- High network usage
- Unnecessary instances

This allows organizations to optimize their cloud spending.

---

## 14. Key Takeaways

- Cloud monitoring continuously observes cloud resources and applications.
- Observability helps understand the internal behavior of systems.
- The three pillars of observability are Metrics, Logs, and Traces.
- Alerts help detect problems quickly.
- Dashboards provide a visual overview of system health.
- Azure provides Azure Monitor, Log Analytics, and Application Insights.
- AWS provides Amazon CloudWatch.
- Monitoring improves reliability, performance, security, and cost optimization.

Day 20 Summary

Topic: Cloud Monitoring & Observability

Main Concepts:

- Cloud Monitoring
- Observability
- Metrics
- Logs
- Traces
- Alerts
- Dashboards
- Azure Monitor
- Log Analytics
- Application Insights
- Amazon CloudWatch
- Cost Monitoring
- Troubleshooting

Learning Outcome:

«I learned how cloud monitoring and observability help organizations monitor resources, detect problems, analyze system behavior, improve performance, and maintain reliable cloud applications.»
