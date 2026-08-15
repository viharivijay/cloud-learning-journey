# ☁️ Day 32 – Cloud Storage & Database Services

## 📅 Day 32 of 50-Day Cloud Learning Journey

Today I learned about **Cloud Storage and Cloud Database Services**, which are essential components of modern cloud applications.

The focus was on understanding different storage types, cloud databases, SQL vs NoSQL databases, storage classes, backups, replication, and choosing the right storage solution for different workloads.

---

## 🎯 Learning Objectives

By the end of Day 32, I learned:

- What Cloud Storage is
- Types of Cloud Storage
- Object Storage
- Block Storage
- File Storage
- Cloud Databases
- SQL Databases
- NoSQL Databases
- Managed Database Services
- Storage Classes
- Lifecycle Management
- Backup and Replication
- Durability vs Availability
- How to select the appropriate storage solution

---

# 1. What is Cloud Storage?

Cloud Storage is a service that allows organizations to store data on cloud infrastructure instead of maintaining physical storage systems.

Cloud storage can be used to store:

- Images
- Videos
- Documents
- Application files
- Backups
- Logs
- Databases
- Machine Learning datasets

### Benefits of Cloud Storage

- Scalability
- High availability
- High durability
- Security
- Accessibility
- Cost efficiency
- Pay-as-you-use pricing

---

# 2. Types of Cloud Storage

The three major types of cloud storage are:

1. Object Storage
2. Block Storage
3. File Storage

---

# 3. Object Storage

Object Storage stores data as objects inside containers such as buckets.

### Examples

- Amazon S3
- Azure Blob Storage
- Google Cloud Storage

### Suitable For

- Images
- Videos
- Documents
- Backups
- Logs
- Data lakes
- Static website files

### Advantages

- Highly scalable
- Highly durable
- Suitable for large amounts of unstructured data
- Easy to access through APIs
- Cost-effective for many workloads

---

# 4. Block Storage

Block Storage divides data into fixed-size blocks and provides storage volumes to virtual machines.

### Examples

- Amazon EBS
- Azure Managed Disks
- Google Persistent Disk

### Suitable For

- Virtual machines
- Operating systems
- Databases
- Enterprise applications
- Applications requiring low-latency storage

### Advantages

- Low latency
- High performance
- Suitable for databases
- Can be attached to compute resources

---

# 5. File Storage

File Storage provides a traditional file-system structure using files and directories.

### Examples

- Amazon EFS
- Azure Files
- Google Filestore

### Suitable For

- Shared application files
- Enterprise applications
- Content management systems
- Shared directories

### Advantages

- Familiar file-system structure
- Supports shared access
- Useful for applications requiring file-based storage

---

# 6. Object vs Block vs File Storage

| Feature | Object Storage | Block Storage | File Storage |
|---|---|---|---|
| Structure | Objects | Blocks | Files & Folders |
| Scalability | Very High | High | High |
| Access | API/HTTP | Storage Volume | File System |
| Best For | Media, backups, logs | VMs, databases | Shared files |
| Example | Amazon S3 | Amazon EBS | Amazon EFS |

### Easy Way to Remember

```text
Object → Files, Media, Backups

Block → Virtual Machines, Databases

File → Shared Files and Folders
