# Cloud Storage & Database Services

##  Overview

Day 32 of my **50-Day Cloud Learning Journey** focused on **Cloud Storage and Database Services**.

I learned how cloud platforms store different types of data and how to select appropriate storage and database technologies based on application requirements.

---

## Topics Covered

- Cloud Storage
- Object Storage
- Block Storage
- File Storage
- Cloud Databases
- SQL Databases
- NoSQL Databases
- Managed Database Services
- Storage Classes
- Lifecycle Management
- Backup
- Replication
- Durability
- Availability
- Storage Selection

---

##  Storage Types

### Object Storage

Used for:

- Images
- Videos
- Backups
- Logs
- Large datasets

Examples:

- Amazon S3
- Azure Blob Storage
- Google Cloud Storage

### Block Storage

Used for:

- Virtual Machines
- Databases
- High-performance applications

Examples:

- Amazon EBS
- Azure Managed Disks
- Google Persistent Disk

### File Storage

Used for:

- Shared files
- Shared directories
- Enterprise applications

Examples:

- Amazon EFS
- Azure Files
- Google Filestore

---

## 🗄️ Database Types

### SQL Databases

SQL databases use structured tables and relationships.

Examples:

- MySQL
- PostgreSQL
- Oracle
- SQL Server
- Amazon RDS
- Azure SQL Database
- Google Cloud SQL

### NoSQL Databases

NoSQL databases provide flexible data models and are designed for highly scalable applications.

Examples:

- MongoDB
- Amazon DynamoDB
- Azure Cosmos DB
- Google Firestore

---

##  SQL vs NoSQL

| SQL | NoSQL |
|---|---|
| Structured data | Flexible data |
| Tables and relationships | Documents/key-value/etc. |
| Fixed schema is common | Flexible schema |
| Strong relational model | Distributed/scalable model |
| Good for transactions | Good for large-scale applications |

---

##  Backup & Replication

### Backup

Creates a copy of data that can be restored when required.

### Replication

Creates additional copies of data to improve availability and resilience.

---

##  Storage Optimization

Cloud storage services provide different storage classes.

```text
Frequently Accessed
        ↓
Infrequent Access
        ↓
Archive
        ↓
Deletion
