# What is AWS RDS?

## Simple Definition

**AWS RDS (Relational Database Service)** is a **managed database service** that lets you create, operate, and scale relational databases without managing the underlying servers.

---

## Interview Answer

> "Amazon RDS is a managed relational database service provided by AWS. It supports databases like MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora. AWS handles backups, patching, monitoring, and maintenance, allowing developers to focus on their applications."

---

## Diagram

```text
         User / Application
                 │
                 ▼
              EC2 App
                 │
                 ▼
          ┌──────────────┐
          │   AWS RDS    │
          │   MySQL DB   │
          └──────────────┘
                 │
         Stores Application Data
```

---

## Real-life Example

🏦 Think of a **bank locker**.

- You store your valuables safely.
- The bank manages the locker building and security.

Similarly:

- **You manage your data.**
- **AWS manages the database server, backups, updates, and maintenance.**

---

## Key Points

- ✅ Managed relational database service.
- ✅ Supports MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Aurora.
- ✅ AWS handles backups, software updates, and maintenance.
- ✅ Easy to scale storage and compute.

---

# Supported Database Engines

- MySQL
- PostgreSQL
- MariaDB
- Oracle
- Microsoft SQL Server
- Amazon Aurora

---

## AWS Connection

A common architecture:

```text
      Users
        │
        ▼
      EC2 App
        │
        ▼
     Amazon RDS
        │
        ▼
   Customer Data
```

Example:

- User registers on your website.
- The application running on EC2 stores the user's details in RDS.

---

## Interview Tip

### Q: Why use RDS instead of installing MySQL on EC2?

**Answer:**

| MySQL on EC2          | Amazon RDS               |
| --------------------- | ------------------------ |
| You manage everything | AWS manages the database |
| Manual backups        | Automatic backups        |
| Manual updates        | Automatic patching       |
| More administration   | Less administration      |

---

## One-line Answer to Remember

> **Amazon RDS is a managed relational database service where AWS manages the database infrastructure, backups, and maintenance.**

---

## ⭐ Common Interview Follow-up Questions

### Q1: Is RDS a managed service?

**Answer:** ✅ Yes.

---

### Q2: Can we SSH into an RDS instance?

**Answer:** ❌ No. You connect using a database client (such as MySQL Workbench or `mysql`), not via SSH.

---

### Q3: Is RDS used for relational databases or NoSQL databases?

**Answer:** **Relational databases.** For NoSQL, AWS provides **DynamoDB**.

---

### Q4: Can multiple EC2 instances connect to one RDS database?

**Answer:** ✅ Yes.

```text
         EC2-1
           │
           ├────────┐
           ▼        │
         Amazon RDS │
           ▲        │
           └────────┤
           │
         EC2-2
```

---

## Easy Way to Remember

```text
EC2  → Virtual Server
S3   → File Storage
RDS  → Relational Database
ELB  → Load Balancer
ASG  → Auto Scaling
IAM  → Access Management
```

### 💡 Interview Tip

A very common interview question is:

**"If your application is running on EC2 and needs to store user data, where would you store it?"**

**Answer:**

> "I would use **Amazon RDS** to store structured data such as user accounts, orders, and product information because it is a managed relational database service that provides automatic backups, patching, and high availability."
