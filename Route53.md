**Amazon Route 53** is AWS's **DNS (Domain Name System) service**.

### Simple Definition

Route 53 connects your **domain name** (e.g., `myapp.com`) to your AWS resources like EC2, Load Balancer, or S3.

### Example

Without Route 53:

```text
http://13.233.45.67
```

With Route 53:

```text
https://myapp.com
```

Users type **`myapp.com`**, and Route 53 translates it to the server's IP address.

### How it works

```text
User types: myapp.com
        │
        ▼
    Route 53 (DNS)
        │
        ▼
    EC2 / Load Balancer / S3
```

### What can Route 53 point to?

- ✅ EC2 Instance
- ✅ Application Load Balancer (ALB)
- ✅ S3 Static Website
- ✅ CloudFront Distribution
- ✅ API Gateway

### Common Use Case

Suppose you've deployed your React app on an EC2 instance.

Current URL:

```text
http://13.233.45.67
```

You buy the domain:

```text
myportfolio.com
```

Using Route 53, you map:

```text
myportfolio.com  →  13.233.45.67
```

Now users visit:

```text
https://myportfolio.com
```

instead of the IP address.

### Interview Definition

> **Amazon Route 53 is a scalable and highly available DNS service that routes users to AWS resources using domain names instead of IP addresses.**

### Full Stack Deployment Flow

```text
User
   │
myapp.com
   │
Route 53
   │
Load Balancer
   │
EC2 (Backend)
   │
RDS / DynamoDB
```

### Easy way to remember

- **EC2** → Runs your application.
- **Route 53** → Maps your domain name to your application.
- **Lambda** → Runs code without servers.
- **DynamoDB** → Stores NoSQL data.

Think of **Route 53 as the internet's phonebook**—it converts human-friendly domain names into the IP addresses computers use to find your application.
