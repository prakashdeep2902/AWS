## What is a Virtual Machine (VM)?

### Simple Definition

A **Virtual Machine (VM)** is a **software-based computer** that runs inside a physical computer. It has its own **CPU, RAM, Storage, and Operating System**.

### Interview Answer

> "A Virtual Machine is a virtual computer created using software. It behaves like a real computer with its own operating system and resources. Multiple VMs can run on a single physical server, which helps save hardware and cost."

### Diagram

```text
              Physical Server
        ┌─────────────────────────┐
        │   Hypervisor            │
        ├─────────────────────────┤
        │  VM 1   │  VM 2 │ VM 3  │
        │ Ubuntu  │ Windows│ Linux│
        │ App A   │ App B  │ App C│
        └─────────────────────────┘
```

### Real-life Example

🏢 Imagine a **large apartment building** (Physical Server).

- Each **apartment** = Virtual Machine (VM)
- Each family lives independently.
- Even though everyone shares the same building, each apartment has its own space.

### Key Points

- ✅ Software-based computer.
- ✅ Has its own Operating System.
- ✅ Multiple VMs can run on one physical server.
- ✅ Saves hardware and reduces cost.

### AWS Connection

In AWS, **EC2 (Elastic Compute Cloud)** is a **Virtual Machine** that you can launch in the cloud.

**Interview Tip:**
If asked, **"Is EC2 a Virtual Machine?"**
👉 **Yes.** EC2 is AWS's virtual machine service.

## What is a Hypervisor?

### Simple Definition

A **Hypervisor** is **software that creates and manages Virtual Machines (VMs)** on a physical server.

### Interview Answer

> "A Hypervisor is a virtualization software that allows multiple Virtual Machines to run on a single physical server. It allocates CPU, RAM, and storage to each VM and keeps them isolated from each other."

### Diagram

```text
          Physical Server
     ┌───────────────────────┐
     │ CPU | RAM | Storage   │
     └──────────┬────────────┘
                │
                ▼
         ┌──────────────┐
         │ Hypervisor   │
         └─────┬────────┘
               │
     ┌─────────┼─────────┐
     ▼         ▼         ▼
   VM 1      VM 2      VM 3
 Ubuntu     Windows    Linux
```

### Real-life Example

🏢 Think of a **hotel manager**.

- 🏨 Hotel = Physical Server
- 👨‍💼 Manager = Hypervisor
- 🛏️ Rooms = Virtual Machines

The manager assigns rooms to guests and makes sure everyone has their own space.

### Key Points

- ✅ Creates and manages Virtual Machines.
- ✅ Shares hardware resources (CPU, RAM, Storage).
- ✅ Keeps VMs isolated from each other.
- ✅ Allows multiple operating systems to run on one physical server.

### AWS Connection

When you launch an **EC2 instance**, AWS uses a **Hypervisor** behind the scenes to create and manage that virtual machine. You don't install or manage the hypervisor yourself—AWS handles it.

### Interview Tip

**Q:** What is the difference between a Hypervisor and a Virtual Machine?

| Hypervisor              | Virtual Machine          |
| ----------------------- | ------------------------ |
| Creates and manages VMs | A virtual computer       |
| Runs on physical server | Runs on the hypervisor   |
| Allocates resources     | Uses allocated resources |

**One-line answer to remember:**

> **Hypervisor creates VMs, and a VM is the virtual computer created by the hypervisor.**
