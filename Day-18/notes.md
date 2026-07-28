# Infrastructure as Code (IaC) with Terraform

## Introduction

Infrastructure as Code (IaC) is the practice of managing and provisioning cloud infrastructure using code instead of manually configuring resources through a cloud portal. By defining infrastructure in configuration files, organizations can automate deployments, maintain consistency, and easily reproduce environments.

Terraform, developed by HashiCorp, is one of the most widely used open-source IaC tools. It allows developers and cloud engineers to create, modify, and manage infrastructure across multiple cloud providers such as Microsoft Azure, AWS, and Google Cloud Platform using a simple declarative language called HCL (HashiCorp Configuration Language).

## What is Infrastructure as Code (IaC)?

Infrastructure as Code is an approach where servers, storage, networking, and other cloud resources are managed through configuration files rather than manual operations.

Instead of repeatedly creating resources through a graphical interface, IaC enables users to define infrastructure once and deploy it consistently whenever needed.

## Why Use Infrastructure as Code?

Traditional infrastructure management often leads to:

Manual configuration errors
Time-consuming deployments
Inconsistent environments
Difficult maintenance
Poor scalability

Infrastructure as Code addresses these challenges by automating the provisioning process and ensuring reliable, repeatable deployments.


## Benefits of Infrastructure as Code

### Automation

Reduces manual effort by automating resource creation and configuration.

### Consistency

Ensures every deployment follows the same configuration, reducing human errors.

### Version Control

Infrastructure code can be stored in Git repositories, enabling change tracking and collaboration.

### Faster Deployment

Entire cloud environments can be provisioned within minutes.

### Easy Maintenance

Updating infrastructure only requires modifying configuration files.

### Disaster Recovery

Infrastructure can be recreated quickly using existing code if resources are lost.

## What is Terraform?

Terraform is an open-source Infrastructure as Code tool that enables users to define and manage cloud infrastructure through code.

It supports multiple cloud providers, allowing organizations to use a single tool to manage resources across different platforms.

Supported Cloud Providers
Microsoft Azure
Amazon Web Services (AWS)
Google Cloud Platform (GCP)
Oracle Cloud
VMware
Digital Ocean

### Terraform Workflow

Terraform follows a simple workflow:

Write Configuration Files
        ↓
terraform in it
        ↓
terraform validate
        ↓
terraform plan
        ↓
terraform apply
        ↓
Infrastructure Created

## Advantages of Terraform
- Open-source and free to use
- Supports multiple cloud providers
- Automates infrastructure deployment
- Easy integration with Git and CI/CD pipelines
- Reusable configurations using modules
- Consistent and repeatable deployments
- Large community and extensive documentation
- Limitations of Terraform
- Initial learning curve for beginners
- State file must be managed securely
- Incorrect configurations may affect infrastructure

## Real-World Applications

Terraform is widely used for:

- Provisioning Azure Virtual Machines
- Creating AWS EC2 Instances
- Deploying Kubernetes Clusters
- Configuring Virtual Networks
- Automating Database Deployment
- Multi-cloud Infrastructure Management
- Disaster Recovery Automation
- Key Terraform Commands Summary

### Key Takeaways
- Infrastructure as Code automates cloud resource management.
- Terraform is one of the leading IaC tools used in cloud environments.
- IaC improves automation, consistency, and scalability.
- Terraform supports multiple cloud providers using a single configuration language.
- Version control enables collaborative infrastructure management.
- Providers, resources, variables, outputs, and state files are the core components of Terraform.
- Terraform is widely adopted in DevOps, Cloud Engineering, and Site Reliability Engineering (SRE).
