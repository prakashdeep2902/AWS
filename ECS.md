## Amazon ECS (Elastic Container Service)

**Amazon ECS** is AWS's **container orchestration service**. It helps you **run, manage, and scale Docker containers**.

### Simple Definition

> **ECS is a service that runs and manages Docker containers on AWS.**

---

## Example

Suppose you have a Dockerized Node.js app.

```text
Node.js App
     │
Docker Image
     │
Amazon ECS
     │
Runs Containers
```

Instead of manually running:

```bash
docker run my-app
```

ECS automatically starts, stops, and scales your containers.

---

## Why use ECS?

- ✅ Run Docker containers
- ✅ Auto Scaling
- ✅ Load Balancing
- ✅ High Availability
- ✅ Easy deployment

---

## ECS Launch Types

1. **EC2**
   - You manage the EC2 instances.
   - ECS runs containers on them.

2. **Fargate**
   - No EC2 management.
   - AWS runs the containers for you (serverless).

---

## Interview (1 line)

> **Amazon ECS is a fully managed container orchestration service that deploys, manages, and scales Docker containers on AWS.**

### Easy way to remember

- **Docker** → Packages your application.
- **ECS** → Runs and manages Docker containers.
- **Fargate** → Runs ECS containers without managing servers.
