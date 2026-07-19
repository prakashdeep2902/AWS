# What is AWS S3?

## Simple Definition

**AWS S3 (Simple Storage Service)** is an **object storage service** used to store and retrieve files like images, videos, documents, backups, and application data.

---

## Interview Answer

> "Amazon S3 is a scalable object storage service provided by AWS. It is used to store and retrieve any amount of data over the internet. S3 is highly durable, secure, and commonly used for storing static website files, backups, images, videos, and logs."

---

## Diagram

```text
          User / Application
                  │
          Upload / Download
                  │
                  ▼
            ┌───────────┐
            │ AWS S3    │
            │  Bucket   │
            └───────────┘
                  │
     ┌────────────┼────────────┐
     ▼            ▼            ▼
  image.jpg    resume.pdf    video.mp4
```

---

## Real-life Example

📦 Think of **S3 as a cloud locker**.

- You create a **locker** → S3 Bucket
- You store your **files** → Objects
- You can access them anytime from anywhere.

---

## Key Points

- ✅ Stores files (objects), not virtual machines.
- ✅ Stores unlimited data.
- ✅ Highly durable (designed for **99.999999999%** durability, often called **11 nines**).
- ✅ Pay only for the storage you use.

---

# Important Terms

### 1. Bucket

A **Bucket** is a container that stores files.

Example:

```text
my-photo-bucket
```

---

### 2. Object

An **Object** is a file stored inside a bucket.

Example:

```text
photo.jpg
resume.pdf
movie.mp4
```

---

### 3. Object Key

The **Object Key** is the file's unique name/path inside the bucket.

Example:

```text
images/profile.jpg
```

---

## AWS Connection

A common architecture is:

```text
User
   │
   ▼
EC2 Application
   │
Uploads Images
   ▼
S3 Bucket
```

Example:

- User uploads a profile picture.
- Your EC2 application stores it in an S3 bucket.

---

## Interview Tip

### Q: What is the difference between EC2 and S3?

| EC2                     | S3                  |
| ----------------------- | ------------------- |
| Virtual Server          | Object Storage      |
| Runs applications       | Stores files        |
| Has an operating system | No operating system |

---

## One-line Answer to Remember

> **Amazon S3 is an object storage service used to securely store and retrieve files in the AWS cloud.**

---

## ⭐ Common Interview Follow-up Questions

1. **What is a Bucket?**
   - A container used to store objects (files).

2. **Can S3 store a database?**
   - No. S3 stores files (objects), not relational databases.

3. **Can we host a static website on S3?**
   - Yes. S3 can host static websites containing HTML, CSS, JavaScript, and images.

4. **Can EC2 access S3?**
   - Yes. The recommended approach is to attach an **IAM Role** to the EC2 instance, allowing it to securely access the S3 bucket without storing access keys.

---

### Easy Way to Remember

```text
EC2 = Compute (Virtual Server)
ELB = Load Balancer
ASG = Auto Scaling
S3  = File Storage
```

This is one of the most common AWS architectures:

```text
             Users
               │
               ▼
             ELB
               │
         ┌─────┴─────┐
         ▼           ▼
       EC2         EC2
         │           │
         └─────┬─────┘
               ▼
            S3 Bucket
       (Images, Videos, Files)
```

This combination is frequently used in production applications and is a favorite topic in AWS interviews.

# What are S3 Storage Classes?

## Simple Definition

**S3 Storage Classes** are different storage options in S3 that help you **balance cost, access speed, and data availability** based on how often you access your data.

---

## Interview Answer

> "S3 Storage Classes are different storage tiers designed for different access patterns. Frequently accessed data uses Standard storage, while infrequently accessed or archived data uses lower-cost storage classes like Standard-IA, Glacier, or Deep Archive."

---

## Diagram

```text
           Frequently Accessed
                   │
                   ▼
             S3 Standard
                   │
         Less Frequently Used
                   ▼
          S3 Standard-IA
                   │
           Rarely Accessed
                   ▼
          S3 Glacier Instant
                   │
         Long-term Archive
                   ▼
             S3 Glacier
                   │
        Very Long-term Archive
                   ▼
         S3 Glacier Deep Archive
```

---

# Common S3 Storage Classes

| Storage Class                     | Best For                                                   |
| --------------------------------- | ---------------------------------------------------------- |
| **S3 Standard**                   | Frequently accessed data                                   |
| **S3 Standard-IA**                | Infrequently accessed data                                 |
| **S3 One Zone-IA**                | Infrequently accessed data stored in one Availability Zone |
| **S3 Glacier Instant Retrieval**  | Rarely accessed data that still needs instant retrieval    |
| **S3 Glacier Flexible Retrieval** | Archives retrieved in minutes or hours                     |
| **S3 Glacier Deep Archive**       | Long-term backups with the lowest storage cost             |

---

## Real-life Example

📚 Think of a library:

- 📖 **S3 Standard** → Books on your study table (used daily).
- 🗄️ **Standard-IA** → Books on a nearby shelf (used occasionally).
- 📦 **Glacier** → Books stored in a warehouse (rarely needed).
- 🏛️ **Deep Archive** → Old records stored in a vault for years.

---

## Key Points

- ✅ **Standard** → Fast access, higher cost.
- ✅ **Standard-IA** → Lower storage cost, retrieval fee applies.
- ✅ **One Zone-IA** → Cheapest IA option, stored in one AZ.
- ✅ **Glacier** → Very low storage cost for archival.
- ✅ **Deep Archive** → Lowest cost, slowest retrieval.

---

## Interview Tip

### Q: Which storage class is best for backups?

**Answer:**

- Regular backups → **Glacier Flexible Retrieval**
- Long-term backups (7–10 years) → **Glacier Deep Archive**

---

### Q: Which storage class is used for a website?

**Answer:**

> **S3 Standard**, because website files (HTML, CSS, JS, images) need fast access.

---

## One-line Answer to Remember

> **S3 Storage Classes let you choose the right balance of cost and performance based on how frequently your data is accessed.**

---

## ⭐ Easy Way to Remember

```text
Frequently Used      → S3 Standard
Sometimes Used       → Standard-IA
Rarely Used          → Glacier Instant
Archive              → Glacier Flexible
Very Long Archive    → Deep Archive
```

### Common Interview Follow-up

**Q: Can an object move automatically between storage classes?**

**Answer:** Yes. By using **S3 Lifecycle Rules**, AWS can automatically move objects between storage classes (for example, from **S3 Standard** to **Standard-IA** and then to **Glacier**) based on rules you define.
