# What is AMI in AWS?

## Simple Definition

**AMI (Amazon Machine Image)** is a **pre-configured template** used to create an EC2 instance (Virtual Machine).

It contains:

- Operating System
- Installed software (optional)
- Configuration settings

---

## Interview Answer

> "An AMI (Amazon Machine Image) is a template used to launch EC2 instances. It includes the operating system, application software, and configuration needed to create a virtual machine."

---

## Diagram

```text
          Amazon Machine Image (AMI)
        ┌──────────────────────────┐
        │ Ubuntu OS                │
        │ Installed Software       │
        │ Configuration            │
        └─────────────┬────────────┘
                      │
                      ▼
              Launch EC2 Instance
                      │
                      ▼
              Running Virtual Machine
```

---

## Real-life Example

🏠 **House Blueprint Analogy**

- 📝 Blueprint = **AMI**
- 🏠 House = **EC2 Instance**

You use a blueprint to build many houses.

Similarly, you use an **AMI** to launch many EC2 instances.

---

## Key Points

- ✅ Used to launch EC2 instances.
- ✅ Contains the Operating System.
- ✅ Can include pre-installed software.
- ✅ One AMI can be used to create multiple EC2 instances.

---

## Types of AMIs

1. **AWS-Provided AMIs**
   - Amazon Linux
   - Ubuntu
   - Windows Server

2. **Custom AMIs**
   - Created by you from your own EC2 instance.

3. **Marketplace AMIs**
   - Provided by third-party vendors with pre-installed software.

---

## Diagram: One AMI → Multiple EC2 Instances

```text
              AMI
               │
      ┌────────┼────────┐
      ▼        ▼        ▼
   EC2-1    EC2-2    EC2-3
```

---

## Interview Tip

### Q: What is the difference between AMI and EC2?

| AMI                | EC2                     |
| ------------------ | ----------------------- |
| Template/Image     | Running Virtual Machine |
| Used to create EC2 | Created from an AMI     |
| Not running        | Running                 |

---

## One-line Answer to Remember

> **AMI is a template, and EC2 is the virtual machine created from that template.**

---

## Easy Memory Trick

Think of it like this:

```text
AMI  +  Instance Type  =  EC2 Instance
(Image) + (CPU & RAM)  =  Virtual Machine
```

- **AMI** → What software to install (OS, apps, configuration)
- **Instance Type** → How powerful the machine is (CPU, RAM)
- **EC2 Instance** → The running virtual server

This is a very common interview question, and remembering this formula makes it easy to answer.
