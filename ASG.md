# What is AWS ASG?

## Simple Definition

**ASG (Auto Scaling Group)** is a service that **automatically adds or removes EC2 instances based on application traffic or demand**.

---

## Interview Answer

> "AWS Auto Scaling Group automatically increases or decreases the number of EC2 instances based on demand. It helps maintain application availability while reducing costs by running only the required number of instances."

---

## Diagram

```text
                 High Traffic 📈
                      │
                      ▼
             Auto Scaling Group
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
      EC2-1         EC2-2         EC2-3
```

When traffic decreases:

```text
                 Low Traffic 📉
                      │
                      ▼
             Auto Scaling Group
                      │
                      ▼
                    EC2-1
```

---

## Real-life Example

🏪 Imagine a supermarket.

- On weekends, many customers visit.
- The manager opens more billing counters.
- On weekdays, fewer customers come, so some counters are closed.

Here:

- Customers = Users
- Billing counters = EC2 Instances
- Manager = Auto Scaling Group

---

## Key Points

- ✅ Automatically launches new EC2 instances when traffic increases.
- ✅ Automatically terminates extra EC2 instances when traffic decreases.
- ✅ Improves availability.
- ✅ Reduces cost by avoiding unnecessary servers.

---

## AWS Connection

ASG is commonly used **with ELB**.

```text
            Users
              │
              ▼
       Elastic Load Balancer
              │
      ┌───────┴────────┐
      ▼                ▼
    EC2-1            EC2-2
        ▲              ▲
        └──────┬───────┘
               │
      Auto Scaling Group
```

- **ELB** distributes traffic.
- **ASG** ensures there are enough EC2 instances.

---

## Interview Tip

### Q: What is the difference between ELB and ASG?

| ELB                    | ASG                            |
| ---------------------- | ------------------------------ |
| Distributes traffic    | Adds/removes EC2 instances     |
| Improves availability  | Improves scalability           |
| Doesn't create servers | Creates and terminates servers |

---

## One-line Answer to Remember

> **ASG automatically scales the number of EC2 instances up or down based on demand.**

---

## ⭐ Easy Way to Remember

- **EC2** → Virtual Server
- **ELB** → Distributes traffic
- **ASG** → Increases or decreases the number of servers

```text
          Users
             │
             ▼
           ELB
             │
     ┌───────┼────────┐
     ▼       ▼        ▼
   EC2-1   EC2-2    EC2-3
             ▲
             │
            ASG
      (Adds/Removes EC2s)
```

### Common Interview Follow-up

**Q: Can ASG work without ELB?**

**Answer:** Yes, but in production they are usually used together. **ASG** manages the number of EC2 instances, while **ELB** distributes traffic among those instances.
