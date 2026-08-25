# Observability & Distributed Tracing 

##  Overview

Day 42 of my Cloud Learning Journey focused on **Observability and Distributed Tracing**, which are essential for monitoring and troubleshooting modern cloud-native and distributed applications.

##  Topics Covered

- Observability fundamentals
- Three pillars of observability
  - Logs
  - Metrics
  - Traces
- Distributed tracing
- Trace vs Span
- Monitoring vs Observability
- OpenTelemetry
- Observability tools
- Alerting
- SLI, SLO and SLA
- Microservices observability
- AI/ML system observability

##  Observability Architecture

```text
Application
     |
     +---- Logs
     |
     +---- Metrics
     |
     +---- Traces
             |
             v
       Open Telemetry
             |
             v
   Observability Platform
        /          \
   Dashboard      Alerts

**Day 42/50 completed**
