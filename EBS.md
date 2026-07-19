# What is AWS EBS (Elastic Block Store)?

## Simple Definition

**Amazon EBS (Elastic Block Store)** is a **persistent block storage service** used to store data for EC2 instances. Think of it as the **hard disk (SSD/HDD)** attached to a virtual machine.

---

## Interview Answer

> "Amazon EBS is a block storage service for EC2 instances. It provides persistent storage, meaning the data remains even if the EC2 instance is stopped. It is commonly used to store the operating system, applications, and user data."

---

## Diagram

```text
          EC2 Instance
     ┌──────────────────┐
     │   Ubuntu/Linux   │
     │   Application    │
     └─────────┬────────┘
               │
               ▼
      ┌──────────────────┐
      │   EBS Volume     │
      │ (Virtual Hard Disk)
      └──────────────────┘
```

---

## Real-life Example

💻 Think of your **laptop**:

- **Laptop** = EC2 Instance
- **Hard Disk (SSD/HDD)** = EBS

Your files are stored on the hard disk, not in RAM.

Similarly:

- EC2 = Computer
- EBS = Hard Disk

---

## Key Points

- ✅ Acts like a **hard disk** for EC2.
- ✅ Stores OS, applications, and data.
- ✅ Data remains even after stopping the EC2 instance.
- ✅ Can be detached from one EC2 instance and attached to another (within the same Availability Zone).

---

## EC2 + EBS Relationship

```text
        EC2 Instance
             │
             ▼
        EBS Volume
             │
      Stores:
      • Operating System
      • Application
      • Database
      • Files
```

---

## Stop vs Terminate

| Action            | What happens to EBS?                                              |
| ----------------- | ----------------------------------------------------------------- |
| **Stop EC2**      | ✅ EBS remains, data is preserved                                 |
| **Terminate EC2** | ❌ Root EBS is deleted by default (unless you change the setting) |

---

## Interview Tip

### Q: What is EBS?

> "Amazon EBS is a persistent block storage service that provides virtual hard disks for EC2 instances. It stores the operating system, applications, and data."

---

## One-line Answer to Remember

> **EBS is the persistent virtual hard disk attached to an EC2 instance.**

---

## ⭐ Common Interview Follow-up

### Q: What is the difference between EBS and S3?

| EBS                 | S3                                               |
| ------------------- | ------------------------------------------------ |
| Block Storage       | Object Storage                                   |
| Attached to EC2     | Accessed over the internet/API                   |
| Used as a hard disk | Used to store files like images, videos, backups |
| Low latency         | Highly scalable storage                          |

**Easy way to remember:**

- 💽 **EBS = Hard Disk**
- 📦 **S3 = File Storage**

This distinction is one of the most common AWS interview questions.
