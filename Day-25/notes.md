# Containerization with Docker

## Introduction

Containerization is a technology that packages an application along with its dependencies, libraries, configuration files, and runtime into a single unit called a container. This ensures that the application runs consistently across different environments, eliminating compatibility issues.

Docker is the most popular containerization platform used to build, package, and deploy applications efficiently.

## Objectives
Understand containerization concepts.
Learn the purpose of Docker.
Explore Docker architecture and components.
Understand Docker Images and Containers.
Learn Dockerfile basics.
Compare Containers and Virtual Machines.
Learn common Docker commands.

## What is Containerization?

Containerization packages applications and all their dependencies into isolated containers that can run consistently on any system.

### Benefits
Consistent application environment
Lightweight and portable
Faster deployment
Easy scalability
Efficient resource utilization

## What is Docker?

Docker is an open-source platform that enables developers to build, ship, and run applications inside containers.

It helps solve the common issue of:

"It works on my machine, but not on yours."

## Docker Architecture

Developer
    │
    ▼
Docker CLI
    │
    ▼
Docker Daemon
    │
    ▼
Docker Images
    │
    ▼
Docker Containers

## Docker Client (CLI)

The command-line interface used to interact with Docker.

Examples:

- docker run
- docker build
- docker pull

### Docker Daemon
The background service responsible for:

- Building images
- Running containers
- Managing networks
- Managing storage volumes

### Docker Registry

A repository used to store Docker images.

Examples:

Docker Hub
Amazon ECR
Azure Container Registry
Google Artifact Registry

## Docker Image

A Docker Image is a read-only template that contains everything required to run an application.

It includes:

- Application code
- Runtime
- Libraries
- Dependencies
- Environment settings

Examples:

python:3.12
ubuntu:22.04
nginx
mysql

## Docker Container

A Docker Container is a running instance of a Docker Image.

One image can create multiple containers.

Docker Image
      │
 ├── Container 1
 ├── Container 2
 └── Container 3

## Docker file

A Docker file is a text file containing instructions to automatically build Docker Images.

### Example:

FROM python:3.12

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python","app.py"]

## Common Docker file Instructions

Instruction  	Description
FROM         Specifies the base image
WORKDIR    	 Sets the working directory
COPY	       Copies files into the image
RUN	         Executes commands during image build
CMD          Specifies the default command
EXPOSE	     Exposes application ports
ENV	         Sets environment variables

## Docker Workflow

Write Code
     │
     ▼
Create Docker file
     │
     ▼
Build Docker Image
     │
     ▼
Run Docker Container
     │
     ▼
Test Application
     │
     ▼
Push Image to Docker Hub
     │
     ▼
Deploy on Cloud


## Common Docker Commands

### Check Docker Version
docker --version

### Download an Image
docker pull ubuntu

### List Images
docker images

### Run a Container
docker run ubuntu

### Run Interactive Container
docker run -it ubuntu bash

### Show Running Containers
docker ps

### Show All Containers
docker ps -a

### Stop a Container
docker stop <container_id>

### Start a Container
docker start <container_id>

### Remove a Container
docker rm <container_id>

### Remove an Image
docker rmi <image_id>

### Build an Image
docker build -t myapp .

### View Container Logs
docker logs <container_id>

### Execute Commands Inside a Container
docker exec -it <container_id> bash

## Docker Hub

Docker Hub is a cloud-based repository used to:

- Store Docker Images
- Share Images
- Download Images
- Manage Image Versions

### Popular Images:

- Ubuntu
- Python
- MySQL
- Nginx
- Node.js

## Docker Image vs Docker Container

Docker Image	                 Docker Container
Blueprint of an application  	 Running instance of an image
Read-only                      Read-write
Static                         Dynamic
Used to create containers	     Executes the application

## Containers vs Virtual Machines
 
Containers	        Virtual Machines
Lightweight	        Heavyweight
Share Host OS	      Separate Guest OS
Fast Startup	Slow  Startup
Lower Memory Usage	Higher Memory Usage
Better Performance	More Resource Consumption

## Docker in Cloud Computing

Docker is widely used for:

- Microservices Architecture
- Web Application Deployment
- AI & Machine Learning
- CI/CD Pipelines
- API Hosting
- Cloud-native Applications
- Testing Environments

### Cloud providers supporting Docker:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Oracle Cloud
- IBM Cloud

## Advantages
- Lightweight
- Portable
- Faster Deployment
- Easy Scalability
- Consistent Environment
- Better Resource Utilization
- Supports DevOps & CI/CD
- Simplified Application Management

## Limitations
- Shares the host operating system kernel
- Less isolated than virtual machines
- Requires proper security configuration
Persistent storage requires additional setup
