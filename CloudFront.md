## Amazon CloudFront

**Amazon CloudFront** is AWS's **Content Delivery Network (CDN)**.

### Simple Definition

CloudFront **stores copies (caches)** of your website's content at locations around the world, so users get content from the nearest location instead of your main server.

### Without CloudFront

```text
User (India)
      │
      ▼
EC2 Server (USA)
```

The user has to fetch data from the USA, which is slower.

### With CloudFront

```text
User (India)
      │
      ▼
CloudFront Edge Location (Mumbai)
      │
      ▼
EC2 / S3 (Origin Server)
```

CloudFront serves cached content from the nearest edge location, making the website much faster.

---

## What can CloudFront serve?

- ✅ Static websites (HTML, CSS, JS)
- ✅ Images
- ✅ Videos
- ✅ APIs
- ✅ Files for download

---

## Example

Suppose your React app is hosted on **S3**.

Without CloudFront:

```text
https://my-bucket.s3.amazonaws.com
```

With CloudFront:

```text
https://d123abcd.cloudfront.net
```

Users receive the website from the nearest AWS edge location.

---

## Benefits

- ✅ Faster loading worldwide
- ✅ Lower latency
- ✅ Reduces load on your server
- ✅ HTTPS support
- ✅ Protection against DDoS attacks (integrates with AWS Shield)

---

## Real-world Architecture

```text
User
   │
Route 53 (myapp.com)
   │
CloudFront
   │
S3 (React App)
   │
API Gateway / Load Balancer
   │
Lambda / EC2
   │
RDS / DynamoDB
```

---

## CloudFront vs Route 53

| Route 53                   | CloudFront                |
| -------------------------- | ------------------------- |
| DNS service                | CDN service               |
| Maps domain to resources   | Caches content near users |
| Example: `myapp.com` → EC2 | Delivers website faster   |

---

## Interview Definition

> **Amazon CloudFront is AWS's Content Delivery Network (CDN) that securely delivers websites, APIs, videos, and other content with low latency by caching it at edge locations around the world.**

### As a Full Stack Developer

A common deployment for a React + Node.js application is:

- **React frontend** → S3
- **CloudFront** → Caches and serves the frontend globally
- **Route 53** → Maps `myapp.com` to CloudFront
- **Backend** → EC2 or Lambda
- **Database** → RDS or DynamoDB

This setup provides fast performance, scalability, and a professional production architecture.

Yes. **CIDR (Classless Inter-Domain Routing)** is a way of defining **IP address ranges**. In AWS, you'll use CIDR every time you create a **VPC** or a **Subnet**.

### Simple Definition

A CIDR block tells AWS:

> **"This network can use these IP addresses."**

### Example

When creating a VPC, you might specify:

```text
10.0.0.0/16
```

This means:

- Network starts at **10.0.0.0**
- `/16` defines the size of the network
- It provides **65,536 IP addresses** (10.0.0.0 to 10.0.255.255)

---

### CIDR Examples

| CIDR Block       | Number of IP Addresses |
| ---------------- | ---------------------: |
| `10.0.0.0/16`    |                 65,536 |
| `10.0.0.0/24`    |                    256 |
| `192.168.1.0/24` |                    256 |
| `172.31.0.0/20`  |                  4,096 |

> **Smaller number after `/` → Larger network**
>
> **Larger number after `/` → Smaller network**

---

### AWS Example

Create a VPC:

```text
VPC CIDR:
10.0.0.0/16
```

Create two subnets inside it:

```text
Public Subnet:
10.0.1.0/24

Private Subnet:
10.0.2.0/24
```

Diagram:

```text
VPC (10.0.0.0/16)
│
├── Public Subnet  (10.0.1.0/24)
│
└── Private Subnet (10.0.2.0/24)
```

Both subnets are part of the VPC because their IP ranges fall within `10.0.0.0/16`.

---

### Why does AWS use CIDR?

- ✅ Defines the IP range for a VPC
- ✅ Divides a VPC into subnets
- ✅ Prevents IP address conflicts
- ✅ Helps route network traffic correctly

---

### Interview Definition

> **CIDR (Classless Inter-Domain Routing) is a notation used to define a range of IP addresses for networks. In AWS, it is used when creating VPCs and subnets to specify their available IP address ranges.**

### Easy way to remember

Think of a **VPC as a city**:

- **CIDR** = the total land area of the city.
- **Subnets** = different neighborhoods within that city.

For AWS interviews, remember these common CIDR blocks:

- `10.0.0.0/16` → Common VPC CIDR
- `10.0.1.0/24` → Public subnet
- `10.0.2.0/24` → Private subnet

These are the examples you'll see most often in tutorials and real AWS environments.

## What is a Subnet?

A **Subnet (Subnetwork)** is a **smaller section of a VPC**.

When you create a VPC, you divide it into one or more subnets to organize and secure your resources.

### Simple Definition

> **A subnet is a range of IP addresses inside a VPC.**

---

## Example

Suppose you create a VPC:

```text
VPC: 10.0.0.0/16
```

Now divide it into two subnets:

```text
Public Subnet : 10.0.1.0/24
Private Subnet: 10.0.2.0/24
```

Diagram:

```text
VPC (10.0.0.0/16)
│
├── Public Subnet (10.0.1.0/24)
│      └── EC2
│
└── Private Subnet (10.0.2.0/24)
       └── RDS
```

---

## Types of Subnets

### 1. Public Subnet 🌐

A public subnet **can access the internet** because its route table points to an **Internet Gateway (IGW)**.

Use it for:

- EC2 Web Servers
- Load Balancers
- Bastion Hosts

---

### 2. Private Subnet 🔒

A private subnet **cannot be accessed directly from the internet**.

Use it for:

- RDS Database
- Internal APIs
- Backend services

---

## Real-world Example

Suppose you deploy a MERN application.

```text
Internet
    │
Internet Gateway
    │
Public Subnet
    │
EC2 (Node.js Backend)
    │
Private Subnet
    │
RDS (MySQL)
```

- Users access the **EC2** server.
- The **RDS database** stays protected because it's in a private subnet.

---

## Why use Subnets?

- ✅ Better security
- ✅ Better organization
- ✅ Separate public and private resources
- ✅ High availability (create subnets in multiple Availability Zones)

---

## Interview Definition

> **A subnet is a logical subdivision of a VPC that contains a specific range of IP addresses. It allows you to organize AWS resources and control whether they are publicly accessible or private.**

---

## VPC vs Subnet

| VPC                       | Subnet                 |
| ------------------------- | ---------------------- |
| Entire private network    | Small part of the VPC  |
| Contains multiple subnets | Contains AWS resources |
| Example: `10.0.0.0/16`    | Example: `10.0.1.0/24` |

---

## Easy Way to Remember

Imagine an apartment building:

- 🏢 **VPC** = The entire apartment building.
- 🚪 **Subnet** = One floor in the building.
- 🏠 **EC2/RDS** = Apartments on that floor.

### For AWS interviews

Remember this common architecture:

```text
VPC
│
├── Public Subnet
│      ├── Load Balancer
│      └── EC2
│
└── Private Subnet
       └── RDS
```

This is the standard production setup you'll encounter in AWS projects and interviews.

### Route Table (AWS)

A **Route Table** is a set of rules that tells AWS **where network traffic should go**.

**Example:**

```text
Destination      Target
0.0.0.0/0        Internet Gateway (IGW)
```

This means:

- Any internet traffic (`0.0.0.0/0`) is sent to the **Internet Gateway**.

### Simple Definition

> **A Route Table controls how traffic is routed within a VPC and to/from the internet.**

**Interview (1 line):**

> **A Route Table is a collection of routing rules that determines the path network traffic takes inside a VPC.**

### NAT Gateway (Network Address Translation)

A **NAT Gateway** allows **resources in a private subnet to access the internet**, while **preventing the internet from initiating connections to them**.

### Example

```text
Internet
    ▲
    │
NAT Gateway
    ▲
    │
Private Subnet (RDS/EC2)
```

### Why use it?

- ✅ Download software updates
- ✅ Install packages (`npm install`, `yum update`)
- ✅ Keep servers private

### Interview (1 line)

> **A NAT Gateway enables outbound internet access for resources in a private subnet without allowing inbound internet traffic.**

### VPC Peering

**VPC Peering** is a connection between **two VPCs** that allows them to communicate using **private IP addresses**.

### Example

```text
VPC A  ⇄  VPC B
```

Resources in both VPCs can communicate as if they are on the same network.

### Why use it?

- ✅ Connect two VPCs securely
- ✅ Share resources between VPCs
- ✅ Use private IPs (no internet)

### Interview (1 line)

> **VPC Peering is a networking connection that enables two VPCs to communicate privately using their private IP addresses.**

### Elastic IP (EIP)

An **Elastic IP** is a **static public IPv4 address** that you can allocate to an AWS resource, such as an EC2 instance.

### Why use it?

- ✅ Public IP doesn't change after stopping/starting an EC2 instance (when associated with the EIP)
- ✅ Easy to remap to another EC2 instance if needed

### Example

```text
Elastic IP
   │
   ▼
EC2 Instance
```

### Interview (1 line)

> **An Elastic IP is a static public IPv4 address in AWS that can be associated with EC2 instances for a fixed public IP address.**
