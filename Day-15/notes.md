# Cloud Containers & Docker Basics

## What are Containers?

Containers are lightweight, portable software packages that contain an application along with all the files, libraries, and dependencies needed to run it consistently on any system.

Unlike virtual machines, containers share the host operating system, making them faster and more resource-efficient.

## Why Containers?

- Fast startup time
- Lightweight and efficient
- Portable across environments
- Consistent application deployment
- Easy scaling and management

## Virtual Machines vs Containers
Virtual Machine       | Container
Has its own OS        | Shares host OS
Larger in size        |  Smaller in size
Slower startup        |  Starts in seconds
Higher resource usage |  Lower resource usage

## What is Docker?

Docker is an open-source platform used to build, package, ship, and run applications inside containers.

## Main Docker Components
- Docker Engine – Runs containers.
- Docker Image – A read-only template used to create containers.
- Docker Container – A running instance of an image.
- Dockerfile – Instructions to build an image.
- Docker Hub – Online repository to store and share Docker images.

## Docker Workflow

Dockerfile
      ↓
Build Image
      ↓
Store Image
      ↓
Run Container

## Common Docker Commands

docker --version
docker pull nginx
docker images
docker run nginx
docker ps
docker stop <container_id>
docker rm <container_id>
docker rmi <image_id>

## Benefits of Docker
- Consistent development and production environments
- Faster application deployment
- Easy application portability
- Better resource utilization
- Supports CI/CD pipelines
- Simplifies microservices deployment

## Real-World Use Cases
- Deploying web applications
- Running microservices
- CI/CD automation
- Cloud-native applications
- Testing and development environments
