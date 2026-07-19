# What is AWS ELB?

## Simple Definition

**ELB (Elastic Load Balancer)** is a service that **distributes incoming traffic across multiple EC2 instances** to improve availability and performance.

---

## Interview Answer

> "AWS Elastic Load Balancer automatically distributes incoming application traffic across multiple EC2 instances. It improves application availability, scalability, and prevents a single server from being overloaded."

---

## Diagram

```text
              Users
                │
                ▼
        ┌──────────────┐
        │     ELB      │
        │ Load Balancer│
        └──────┬───────┘
               │
      ┌────────┴────────┐
      ▼                 ▼
   EC2 - 1           EC2 - 2
 (App Server)      (App Server)
```

---

## Real-life Example

🏦 Think of a **bank**.

- Customers enter the bank.
- A receptionist sends each customer to an available cashier.
- No single cashier gets overloaded.

Here:

- Customers = Users
- Receptionist = ELB
- Cashiers = EC2 Instances

---

## Key Points

- ✅ Distributes traffic across multiple EC2 instances.
- ✅ Prevents server overload.
- ✅ Improves High Availability.
- ✅ Automatically works with Auto Scaling.

---

## Types of Load Balancers

| Type                                | Used For                                              |
| ----------------------------------- | ----------------------------------------------------- |
| **Application Load Balancer (ALB)** | HTTP/HTTPS web applications                           |
| **Network Load Balancer (NLB)**     | High-performance TCP/UDP traffic                      |
| **Gateway Load Balancer (GWLB)**    | Third-party network appliances (firewalls, IDS, etc.) |

👉 **For most web applications, you'll use ALB.**

---

## AWS Connection

A typical production setup looks like this:

```text
Users
   │
   ▼
 Application Load Balancer (ALB)
   │
   ├────────► EC2-1
   ├────────► EC2-2
   └────────► EC2-3
```

If one EC2 instance fails, ELB automatically sends traffic to the healthy instances.

---

## Interview Tip

### Q: Why do we use ELB?

**Answer:**

- To distribute traffic.
- To improve application availability.
- To avoid overloading a single server.
- To work with Auto Scaling for better scalability.

---

## One-line Answer to Remember

> **AWS ELB automatically distributes incoming traffic across multiple EC2 instances to improve availability, scalability, and performance.**
