# Terraform (Infrastructure as Code)

## 1. What is Ansible?
Ansible is an open-source automation and configuration-management tool used to automate tasks across servers and cloud infrastructure.
It can automate:
Server configuration
Software installation
Application deployment
User management
Service management
Cloud infrastructure tasks
Repetitive administrative operations
Simple example
Instead of manually installing Python on 10 servers, you can write one Ansible playbook and install it on all 10 servers automatically.

## 2. Why Do We Need Ansible?
Suppose an organization has:
50 Linux servers
20 application servers
10 database servers
Doing configuration manually would be:
❌ Slow
❌ Error-prone
❌ Difficult to maintain
❌ Difficult to reproduce
With Ansible:
Administrator
      ↓
   Ansible
      ↓
 ┌────┼────┐
 ↓    ↓    ↓
S1   S2   S3
One automation process can configure multiple machines.

## 3. Important Features of Ansible
🔹 Agentless
Ansible doesn't require an agent to be installed on managed Linux machines.
🔹 Simple
Ansible uses YAML, which is easy to read and understand.
🔹 Idempotent
Ansible generally attempts to make the system reach a desired state without unnecessarily repeating changes.
🔹 Automation
It automates repetitive infrastructure and deployment tasks.
🔹 Secure
Linux/Unix systems commonly use SSH for communication.
🔹 Scalable
It can manage anything from a few servers to large infrastructures.

## 4. Ansible Architecture
Ansible mainly consists of:
1. Control Node
The machine where Ansible is installed.
It sends instructions to managed machines.
2. Managed Nodes
The servers/machines that Ansible manages.
3. Inventory
A file containing information about managed hosts.
Example:
[webservers]
web1
web2

[databases]
db1
db2
4. Playbook
A YAML file containing automation instructions.
5. Modules
Reusable units of code that perform specific tasks.
Examples:
apt
yum
copy
file
service
user
command
6. Tasks
Individual actions performed by Ansible.

## 5. Ansible Workflow
          Control Node
               ↓
        Ansible Playbook
               ↓
           Inventory
               ↓
        Ansible Modules
               ↓
     ┌─────────┼─────────┐
     ↓         ↓         ↓
   Server 1  Server 2  Server 3
## 6. What is YAML?
Ansible playbooks are commonly written in YAML.
YAML stands for:
YAML Ain't Markup Language
Example:
- name: Install Nginx
  hosts: webservers
  become: yes

  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present
This tells Ansible to install Nginx on machines belonging to the webservers group.

## 7. What is an Inventory?
Inventory tells Ansible which machines it needs to manage.
Example:
[webservers]
192.168.1.10
192.168.1.11

Example:
---
- name: Configure Web Server
  hosts: webservers
  become: yes

  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present

    - name: Start nginx
      service:
        name: nginx
        state: started
Structure
Playbook
   ↓
Play
   ↓
Tasks
   ↓
Modules

## 9. Ansible Modules
Modules are the building blocks of Ansible automation.
Module
Purpose
apt
Install packages on Debian/Ubuntu
yum
Manage packages on RHEL-based systems
copy
Copy files
file
Manage files/directories
service
Manage services
user
Manage users
command
Execute commands
shell
Execute shell commands

## 10. Ansible vs Terraform
This is especially important because you learned Terraform on Day 18.
Terraform
Ansible
Infrastructure provisioning
Configuration management
Creates infrastructure
Configures infrastructure
Uses HCL
Uses YAML
Declarative
Declarative
Excellent for cloud resources
Excellent for servers/software
IaC tool
Automation/configuration tool
Example
Terraform:
"Create an Azure VM."
Ansible:
"Install Python, configure Nginx and deploy my application on that VM."
They can therefore be used together.
Terraform
    ↓
Creates Cloud Infrastructure
    ↓
Virtual Machine
    ↓
Ansible
    ↓
Configures VM
    ↓
Deploy Application
