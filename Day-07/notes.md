# Cloud Networking Fundamentals

## What is Cloud Networking?
Cloud networking is the process of connecting cloud resources such as virtual machines, storage, databases, and applications over a secure virtual network. It allows communication between cloud services, users, and the internet while ensuring security, scalability, and reliability.

### Key Features
- Secure communication
- High availability
- Scalability
- Flexible network management
- Easy remote access

## Virtual Private Cloud (VPC)
A Virtual Private Cloud (VPC) is a logically isolated virtual network within a public cloud where you can launch and manage cloud resources securely.

### Features
- Isolated network environment
- Custom IP address ranges
- Public and private subnets
- Route tables for traffic management
- Security Groups and Network ACLs for protection
  
### Advantages
- Enhanced security
- Better control over networking
- Easy scalability
- Cost-effective resource management

## Subnets
A Subnet is a smaller section of a VPC that helps organize and isolate cloud resources.

### Public Subnet
A public subnet contains resources that can communicate directly with the internet through an Internet Gateway.

#### Examples
- Web Servers
- Load Balancers

### Private Subnet
A private subnet contains resources that are not directly accessible from the internet.

#### Examples
- Databases
- Application Servers

### Benefits of Subnets
- Improved security
- Better network organization
- Efficient traffic management
- Easier resource isolation

## IP Addressing
An IP Address is a unique identifier assigned to each device or cloud resource.

### Public IP
- Accessible from the internet.
- Used for public-facing applications.

### Private IP
- Used only within the private cloud network.
- Not directly accessible from the internet.

### Static IP
- Remains the same over time.
- Suitable for web servers and DNS servers.

### Dynamic IP
- Assigned automatically and may change.
- Commonly used for client devices.

## Internet Gateway (IGW)
An Internet Gateway is a networking component that allows communication between a VPC and the public internet.

### Functions
- Enables inbound internet traffic
- Enables outbound internet traffic
- Connects public subnets to the internet
  
### Advantages
- Public accessibility
- High availability
- Managed by the cloud provider

## NAT Gateway
A Network Address Translation (NAT) Gateway allows resources in a private subnet to access the internet for updates and downloads without allowing inbound internet connections.

### Benefits
- Improved security
- Internet access for private resources
- Prevents direct external access
  
## Route Tables
A Route Table contains rules that determine where network traffic should be directed.

### Types
- Default Route
- Custom Route

### Purpose
- Directs traffic efficiently
- Connects subnets
- Controls internet access
  
## Security Groups
A Security Group acts as a virtual firewall for individual cloud resources.

### Characteristics
- Instance-level security
- Stateful
- Controls inbound and outbound traffic

### Advantages
- Easy to configure
- Strong security
- Flexible access control

## Network ACL (Access Control List)
A Network ACL is a firewall that controls traffic at the subnet level.

### Characteristics
- Subnet-level security
- Stateless
- Supports allow and deny rules

### Advantages
- Additional layer of protection
- Controls traffic for all resources in a subnet
- Improves network security
  
## Real-World Example
Consider an online shopping website:

- **VPC** hosts all cloud resources.
- **Public Subnet** contains the web server accessible to customers.
- **Private Subnet** contains the database storing customer information.
- **Internet Gateway** allows customers to access the website.
- **NAT Gateway** allows the database server to download updates without being publicly accessible.
- **Security Groups** protect individual servers.
- **Network ACLs** protect the entire subnet.

## Key Takeaways
- Cloud networking enables secure communication between cloud resources.
- A VPC provides an isolated network in the cloud.
- Public subnets host internet-facing resources, while private subnets host sensitive resources.
- Internet Gateway provides public internet access.
- NAT Gateway enables secure outbound internet access for private resources.
- Route Tables control the path of network traffic.
- Security Groups protect individual instances, while Network ACLs protect entire subnets.
