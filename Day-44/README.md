#  Infrastructure as Code (IaC)

IaC is the practice of managing and provisioning infrastructure using **machine-readable configuration files** instead of manual setup.  
It enables **automation, consistency, scalability, and version control** in cloud environments.

---

##  Objectives
- Understand IaC fundamentals  
- Learn Terraform architecture & workflow  
- Explore providers, resources, variables, outputs, and state  
- Practice Terraform commands  
- Compare Terraform vs CloudFormation  
- Apply IaC best practices  

---

##  What is IaC?
- **Traditional:** Manual setup via cloud console → prone to errors  
- **IaC:** Configuration files → IaC tool → Cloud provider → Resources  

---

## Why IaC Matters
-  Automation  
-  Consistency & reproducibility  
-  Version control with Git  
-  Faster deployments  
-  Reduced human errors  
-  Scalability across environments  

---

##  Terraform Basics
- **Open-source IaC tool** (declarative approach)  
- Supports multi-cloud (AWS, Azure, GCP, Kubernetes, GitHub, etc.)  

###  Architecture
Configuration → Provider → API Calls → Cloud Provider → Infrastructure  

### Common Files
| File              | Purpose                          |
|-------------------|----------------------------------|
| `main.tf`         | Main infra config                |
| `variables.tf`    | Input variables                  |
| `outputs.tf`      | Output values                    |
| `providers.tf`    | Provider config                  |
| `terraform.tfvars`| Variable values                  |
| `terraform.tfstate`| State file (infra record)       |

---

## 🛠️ Key Concepts
- **Provider:** Connects Terraform to a platform  
  ```hcl
  provider "aws" { region = "us-east-1" }

## Day 44/50 completed
