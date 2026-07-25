# Kubernetes Fundamentals (Container Orchestration)

## What is Kubernetes?

Kubernetes (often abbreviated as K8s) is an open-source platform used to deploy, manage, scale, and automate containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).
While Docker creates and runs containers, Kubernetes manages large numbers of containers across multiple servers.

## Why Kubernetes?

Managing containers manually becomes difficult when applications grow.

**Kubernetes helps by:**
- Automatically deploying containers
- Restarting failed containers
- Scaling applications based on demand
- Load balancing traffic
- Performing rolling updates with minimal downtime
- Managing container networking and storage

## Kubernetes Architecture

### Control Plane
- API Server
- Scheduler
- Controller Manager
- etcd (stores cluster data)

### Worker Node
- Kubelet
- Container Runtime
- Kube Proxy
- Pods

## Important Kubernetes Components

### Pod
The smallest deployable unit in Kubernetes containing one or more containers.

### Node
A physical or virtual machine where Pods run.

### Cluster
A collection of nodes managed by Kubernetes.

### Deployment
Maintains the desired number of Pods and enables updates.

### Service
Provides a stable network endpoint for Pods.

### Namespace
Separates resources within the same cluster.

## Kubernetes Features

- Automatic Scaling
- Self-Healing
- Load Balancing
- Rolling Updates
- Rollbacks
- Service Discovery
- Secret Management
- Persistent Storage

## Kubernetes Workflow

- Build a Docker image.
- Push it to a container registry.
- Create Kubernetes deployment files.
- Deploy the application.
- Kubernetes schedules Pods on nodes.
- Services expose the application to users.

## Real-World Uses

- Netflix
- Spotify
- Airbnb
- Google Cloud
- Microsoft Azure
- Amazon Web Services (AWS)

## Key Terms

- Kubernetes (K8s)
- Cluster
- Node
- Pod
- Deployment
- ReplicaSet
- Service
- Namespace
- Control Plane
- Worker Node

## Key Takeaways
- Kubernetes automates container deployment and management.
- Pods are the smallest deployable units.
- Deployments ensure the desired number of Pods are running.
- Services provide stable networking for applications.
- Kubernetes offers scalability, self-healing, and high availability.
