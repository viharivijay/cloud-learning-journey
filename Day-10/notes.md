# Containers and Containerization (Docker Basics)

## What is a Container?
A container is a lightweight, portable package that includes an application along with all its dependencies, libraries, and configuration files. It ensures the application runs consistently across different environments.

## What is Containerization?
Containerization is the process of packaging an application and its dependencies into a container so it can run reliably on any system.

## Containers vs Virtual Machines

**Containers**           | **Virtual Machines**
Lightweight              | Heavier
Share the host OS kernel | Each VM has its own OS
Faster startup           | Slower startup
Lower resource usage     | Higher resource usage
Best for microservices   | Best for running multiple operating systems

## What is Docker?
Docker is an open-source platform used to build, package, distribute, and run containers.

## Docker Components

- **Docker Engine** - Runs containers.
- **Docker Image** – A template used to create containers.
- **Docker Container** – A running instance of an image.
- **Docker Hub** – An online repository for Docker images.

## Benefits of Containers

- Faster application deployment.
- Consistent environments across development and production.
- Better resource utilization.
- Easy scalability.
- Supports microservices architecture.

## Container Use Cases

- Web applications
- Microservices
- CI/CD pipelines
- Cloud-native applications
- DevOps workflows
