# What is AWS EC2?

## Simple Definition

**AWS EC2 (Elastic Compute Cloud)** is a service that lets you **create and run virtual servers (Virtual Machines) in the AWS cloud**.

---

## Interview Answer

> "Amazon EC2 is a compute service that provides virtual machines in the cloud. It allows us to launch, manage, and scale servers without buying physical hardware. We can choose the operating system, CPU, memory, and storage based on our application needs."

---

## Diagram

```text
                 Developer
                     │
                     ▼
             Launch EC2 Instance
                     │
                     ▼
          ┌────────────────────┐
          │     AWS Cloud      │
          │                    │
          │   EC2 Instance     │
          │  (Virtual Machine) │
          │ Ubuntu / Windows   │
          └────────────────────┘
                     │
                     ▼
              Run Your Application
```

---

## Real-life Example

🏠 Imagine you need a computer to run your application.

- **Traditional way:** Buy a physical computer.
- **AWS way:** Rent a virtual computer (EC2) from AWS and use it only when needed.

---

## Key Points

- ✅ EC2 is a **Virtual Machine (VM)**.
- ✅ You can choose the operating system (Ubuntu, Amazon Linux, Windows, etc.).
- ✅ You can start, stop, reboot, or terminate the instance.
- ✅ Pay only for the time/resources you use.

---

# EC2 Components

### 1. AMI (Amazon Machine Image)

An **AMI is a template** used to create an EC2 instance.

It includes:

- Operating System
- Installed software (optional)
- Configuration

Example:

- Ubuntu AMI
- Amazon Linux AMI
- Windows Server AMI

**Think of an AMI as a blueprint or image of a computer.**

---

### 2. Instance Type

Defines the **hardware configuration** of your EC2 instance.

Examples:

- `t2.micro`
- `t3.micro`
- `m5.large`

It determines:

- CPU
- Memory (RAM)
- Network performance

---

### 3. Key Pair

A **Key Pair** is used to securely log in to your EC2 instance.

- **Public Key** → Stored on the EC2 instance.
- **Private Key (.pem file)** → Kept by you.

```text
Your Computer
    │
Private Key (.pem)
    │
    ▼
EC2 Instance
Public Key
```

Without the private key, you usually can't SSH into the instance.

---

### 4. Security Group

A **Security Group acts as a virtual firewall** for the EC2 instance.

It controls:

- Incoming (Inbound) traffic
- Outgoing (Outbound) traffic

Example:

- Allow SSH (Port 22)
- Allow HTTP (Port 80)
- Allow HTTPS (Port 443)

---

### 5. EBS (Elastic Block Store)

EBS is the **hard disk** attached to the EC2 instance.

It stores:

- Operating system
- Applications
- Files
- Data

---

## Interview Tip

### Q: What is EC2?

> "EC2 is a service that provides resizable virtual servers in the AWS cloud. It allows users to run applications without managing physical hardware."

---

### Q: What is the difference between EC2 and a Physical Server?

| EC2               | Physical Server          |
| ----------------- | ------------------------ |
| Virtual Machine   | Real hardware            |
| Runs in AWS Cloud | Runs in your data center |
| Easily scalable   | Hard to scale            |
| Pay-as-you-go     | High upfront cost        |

---

## One-line Answer to Remember

> **Amazon EC2 is AWS's service for creating and managing virtual machines (servers) in the cloud.**

---

## ⭐ Common Interview Follow-up Questions

After EC2, interviewers often ask:

1. What is an **AMI**?
2. What is the purpose of a **Key Pair**?
3. What is a **Security Group**?
4. What is the difference between **EBS** and **Instance Store**?
5. What happens when you **stop** vs **terminate** an EC2 instance?
6. How do you connect to an EC2 instance using SSH?

These are some of the most frequently asked EC2 interview questions, so they're worth learning next.
