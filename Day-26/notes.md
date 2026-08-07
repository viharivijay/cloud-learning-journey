# Containerization with Docker

## What is Containerization?

Containerization is a lightweight virtualization method where applications and all their dependencies are packaged into a container. This ensures the application runs consistently across different environments.

Unlike virtual machines, containers share the host operating system kernel, making them faster and more efficient.

## What is Docker?

Docker is an open-source platform used to:

Build applications
Package applications into containers
Ship applications
Run applications consistently anywhere

Docker solves the common problem:

"It works on my machine but not on yours."

## Why Use Docker?
Advantages:
Lightweight
Fast startup
Portable
Platform independent
Efficient resource utilization
Easy deployment
Simplifies application management
Supports microservices architecture

## Docker Architecture

+----------------------+
|     Docker Client    |
+----------+-----------+
           |
           v
+----------------------+
|     Docker Daemon    |
| (Build, Run Images)  |
+----------+-----------+
           |
           |
   +-------+--------+
   |                |
   v                v
Docker Images   Docker Containers

## Docker Components

### 1. Docker Client

The command-line interface where users execute Docker commands.

Example:

docker run nginx

### 2. Docker Daemon

Runs in the background.

Responsible for:

Creating images
Running containers
Managing Docker objects

### 3. Docker Image

A read-only blueprint used to create containers.

Contains:

Application code
Runtime
Libraries
Dependencies

Examples:

Ubuntu
Python
Node.js
Nginx

### 4. Docker Container

A running instance of a Docker image.

You can:

Start
Stop
Restart
Delete

### 5. Docker Hub

Cloud repository for Docker images.

Similar to GitHub but for Docker images.

Contains thousands of ready-made images.

Examples:

nginx
mysql
redis
python
ubuntu

## Virtual Machine vs Docker

Virtual Machine        	Docker Container
Heavy	                  Lightweight
Own Operating System	  Shares Host OS
Slow Startup	          Starts in Seconds
Large Storage	          Small Size
Less Efficient	        Highly Efficient
Uses Hypervisor	        Uses Docker Engine

## Docker Lifecycle

Dockerfile
      ↓
Build Image
      ↓
Store Image
      ↓
Run Container
      ↓
Stop Container
      ↓
Remove Container

## Docker Installation

### Windows

Install Docker Desktop.

Linux
sudo apt update

sudo apt install docker.io

Check version

docker --version

## Basic Docker Commands

### Check Docker Version
docker --version
### Show Docker Information
docker info
### Download an Image
docker pull ubuntu
### List Images
docker images
### Run a Container
docker run ubuntu
### Run Interactive Container
docker run -it ubuntu bash
### List Running Containers
docker ps
### List All Containers
docker ps -a
### Stop Container
docker stop <container_id>
### Remove Container
docker rm <container_id>
### Remove Image
docker rmi <image_id>

## Docker Image Workflow

Docker file
      ↓
docker build
      ↓
Docker Image
      ↓
docker run
      ↓
Running Container

## Real-World Use Cases
- Web application deployment
- Microservices
- CI/CD pipelines
- Machine Learning environments
- API deployment
- Cloud-native applications
- DevOps automation
- Testing environments

## Benefits of Docker in Cloud Computing
- Consistent application deployment
- Easy scaling
- Faster software delivery
- Better resource utilization
- Simplified dependency management
- Supports Kubernetes orchestration
- Enables DevOps practices
