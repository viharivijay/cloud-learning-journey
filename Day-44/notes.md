# Infrastructure as Code (IaC)

##  Overview

Infrastructure as Code (IaC) is the practice of managing and provisioning cloud infrastructure using machine-readable configuration files instead of manually creating resources through a cloud provider's console.

IaC helps organizations create infrastructure that is automated, repeatable, consistent, version-controlled, and scalable.


---

## Learning Objectives

Understand Infrastructure as Code

Learn the benefits of IaC

Understand Terraform fundamentals

Learn Terraform architecture and workflow

Understand providers, resources, variables, outputs, and state

Learn basic Terraform commands

Understand Terraform vs CloudFormation

Learn IaC best practices



---

## 1. What is Infrastructure as Code?

Infrastructure as Code allows infrastructure to be described using configuration files.

Instead of manually creating:

Virtual machines

Networks

Databases

Storage

Security groups


we define them in code and allow an IaC tool to create and manage them.

Traditional Approach

Cloud Console
     ↓
Manual Configuration
     ↓
Cloud Resources

IaC Approach

Configuration Files
        ↓
    IaC Tool
        ↓
Cloud Provider
        ↓
Cloud Resources


---

## 2. Why is IaC Important?

🔹 Automation

Infrastructure can be created automatically.

🔹 Consistency

The same configuration can be deployed repeatedly.

🔹 Version Control

Infrastructure code can be stored in Git and tracked like application code.

🔹 Faster Deployment

Large environments can be provisioned quickly.

🔹 Reduced Human Errors

Automation reduces mistakes caused by manual configuration.

🔹 Scalability

Infrastructure can easily be replicated for different environments.

🔹 Reproducibility

Development, testing, and production environments can use consistent configurations.


---

## 3. Terraform

Terraform is an open-source IaC tool used to define and provision infrastructure using configuration files.

Terraform uses a declarative approach.

You specify what the desired infrastructure should look like, and Terraform determines the actions required to achieve that state.


---

## 4. Terraform Architecture

Terraform Configuration
        ↓
     Provider
        ↓
Terraform API Calls
        ↓
 Cloud Provider
        ↓
Infrastructure

Terraform can work with many providers and services.

Examples include:

AWS

Microsoft Azure

Google Cloud

Kubernetes

GitHub

Cloudflare



---

## 5. Terraform Configuration Files

Terraform configuration files normally use the .tf extension.

Example:

main.tf
variables.tf
outputs.tf
providers.tf
terraform.tfstate

Common Files

File	Purpose

main.tf	Main infrastructure configuration
variables.tf	Input variables
outputs.tf	Output values
providers.tf	Provider configuration
terraform.tfvars	Variable values
terraform.tfstate	Terraform state



---

## 6. Terraform Provider

A provider allows Terraform to communicate with an external platform or cloud service.

Example:

provider "aws" {
  region = "us-east-1"
}

Here:

aws → provider

us-east-1 → AWS region



---

## 7. Terraform Resource

A resource represents infrastructure that Terraform creates or manages.

Example:

resource "aws_s3_bucket" "example" {
  bucket = "my-example-bucket"
}

Structure:

resource "TYPE" "NAME" {
    configuration
}


---

## 8. Variables

Variables allow configurations to be reusable and flexible.

Example:

variable "region" {
  type    = string
  default = "us-east-1"
}

Using the variable:

provider "aws" {
  region = var.region
}


---

## 9. Outputs

Outputs display useful information after Terraform creates infrastructure.

Example:

output "bucket_name" {
  value = aws_s3_bucket.example.bucket
}

Outputs can be useful for:

Resource IDs

IP addresses

URLs

DNS names

Resource names



---

## 10. Terraform State

Terraform maintains information about managed infrastructure in a state file.

Default state file:

terraform.tfstate

Terraform uses the state to understand:

What resources it manages

Current infrastructure state

Changes between configuration and infrastructure


⚠️ Important

The Terraform state file can contain sensitive information.

For team environments, remote state storage and appropriate access controls should be used.


---

## 11. Terraform Workflow

The basic Terraform workflow is:

Write Configuration
        ↓
terraform init
        ↓
terraform plan
        ↓
terraform apply
        ↓
Infrastructure Created


---

terraform init

Initializes the Terraform working directory and downloads required providers.

terraform init


---

terraform plan

Shows what Terraform intends to change.

terraform plan

It helps you review changes before applying them.


---

terraform apply

Creates or updates infrastructure.

terraform apply


---

terraform destroy

Removes resources managed by Terraform.

terraform destroy

⚠️ Use carefully because it can delete infrastructure.


---

## 12. Terraform Example

A simple AWS S3 example:

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "example" {
  bucket = "my-unique-example-bucket"
}

Basic workflow:

terraform init
terraform plan
terraform apply

When the infrastructure is no longer required:

terraform destroy


---

## 13. Declarative vs Imperative

Imperative

You describe how something should be done.

Create server
Install software
Configure network
Start service

Declarative

You describe what the final state should be.

I need:
1 server
1 network
1 database

Terraform primarily follows the declarative approach.


---

## 14. Terraform vs Cloud Formation

Feature	Terraform	AWS Cloud Formation

Type	IaC tool	AWS IaC service
Cloud Support	Multi-cloud	AWS-focused
Configuration	HCL	YAML/JSON
State	Terraform state	Managed through CloudFormation
AWS Integration	Strong	Native
Portability	High	Lower
Ecosystem	Large provider ecosystem	AWS ecosystem


Simple Difference

Terraform: Multi-cloud IaC

CloudFormation: AWS-native IaC


---

## 15. Infrastructure as Code Best Practices

✅ Store IaC code in Git
✅ Use reusable modules
✅ Separate development and production environments
✅ Use variables instead of hardcoding values
✅ Protect state files
✅ Use remote state for team environments
✅ Review terraform plan before applying changes
✅ Avoid committing secrets
✅ Use version-controlled configurations
✅ Follow least-privilege IAM principles
✅ Automate infrastructure testing and deployment


---

## 16. IaC in DevOps

IaC is an important part of modern DevOps workflows.

Developer
    ↓
Git Repository
    ↓
CI/CD Pipeline
    ↓
Terraform
    ↓
Cloud Provider
    ↓
Infrastructure

Infrastructure changes can therefore go through:

Code → Review → Testing → Approval → Deployment


---

## 17. Key Advantages

Without IaC

Manual Setup
     ↓
Configuration Differences
     ↓
Human Errors
     ↓
Difficult Reproduction

With IaC

Code
 ↓
Automation
 ↓
Consistency
 ↓
Version Control
 ↓
Repeatable Infrastructure


---

## 18. Key Terms

Term	Meaning

IaC	Infrastructure as Code
Terraform	IaC automation tool
Provider	Connects Terraform to a platform
Resource	Infrastructure managed by Terraform
Variable	Configurable input
Output	Information returned after deployment
State	Terraform's record of managed infrastructure
Module	Reusable Terraform configuration
Plan	Preview of infrastructure changes
Apply	Applies infrastructure changes
Destroy	Removes managed infrastructure



---

## Interview Questions

1. What is Infrastructure as Code?

IaC is the practice of defining and managing infrastructure using code or configuration files rather than manually configuring resources.

2. What is Terraform?

Terraform is an open-source declarative IaC tool used to provision and manage infrastructure across different cloud and service providers.

3. What is Terraform state?

Terraform state is a record that Terraform uses to track and manage the infrastructure resources defined in its configuration.

4. What is terraform plan?

It previews the changes Terraform intends to make without actually applying them.

5. What is terraform apply?

It applies the planned configuration changes to create, modify, or remove infrastructure.

6. What is a Terraform provider?

A provider is a plugin that allows Terraform to communicate with a specific cloud platform, service, or API.

7. What is the difference between Terraform and CloudFormation?

Terraform is designed to work across multiple providers and clouds, whereas CloudFormation is primarily designed for AWS infrastructure.


---

## Practice the Terraform workflow:

terraform init
terraform validate
terraform plan
terraform apply
terraform destroy

## Mini Project

Project: AWS Infrastructure Provisioning with Terraform

Create a simple AWS environment containing:

S3 bucket

Configurable AWS region

Terraform variables

Terraform outputs

Proper Git repository structure


Document the architecture and Terraform commands in your README.


---

## Day 44 Summary

Today I learned Infrastructure as Code (IaC) and how it enables automated cloud infrastructure management. I studied Terraform fundamentals, providers, resources, variables, outputs, state management, and the Terraform workflow. I also learned the differences between Terraform and AWS CloudFormation and explored IaC best practices.

## Key Takeaway

> IaC transforms infrastructure management from manual configuration into automated, version-controlled, repeatable code.



Day 44 Status: ✅ Completed
