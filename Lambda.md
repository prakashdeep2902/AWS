**AWS Lambda** is a **serverless compute service** that lets you run code **without managing servers**.

### Simple Definition

Instead of creating an EC2 instance, installing Node.js, and running your application, you simply upload your code to Lambda. AWS runs it whenever it's triggered.

### How it works

```
User Request
      │
      ▼
 API Gateway
      │
      ▼
 AWS Lambda
      │
      ▼
 DynamoDB / RDS / S3
```

### Example (Node.js)

Suppose you have a function that returns "Hello World".

```javascript
exports.handler = async (event) => {
  return {
    statusCode: 200,
    body: "Hello World",
  };
};
```

When someone calls your API, Lambda runs this code and returns the response.

### What can trigger a Lambda?

- 🌐 API Gateway (HTTP requests)
- 📁 S3 (file upload)
- 🗄️ DynamoDB (data changes)
- ⏰ EventBridge (scheduled jobs)
- 📬 SQS (messages)
- 🔔 SNS (notifications)

### Why use Lambda?

- ✅ No server management
- ✅ Auto-scales automatically
- ✅ Pay only when your code runs
- ✅ Supports Node.js, Python, Java, Go, .NET, etc.

### Example in a Full Stack App

Suppose you have a React frontend.

1. User clicks **"Create User"**.
2. React sends a request to **API Gateway**.
3. API Gateway triggers **Lambda**.
4. Lambda stores the data in **DynamoDB** (or RDS).
5. Lambda returns a success response.

### EC2 vs Lambda

| EC2                        | Lambda                                        |
| -------------------------- | --------------------------------------------- |
| You manage the server      | AWS manages the server                        |
| Runs continuously          | Runs only when triggered                      |
| Pay for running instance   | Pay only for execution time                   |
| Good for long-running apps | Good for APIs, automation, event-driven tasks |

### Interview Definition

> **AWS Lambda is a serverless compute service that executes code in response to events without requiring you to provision or manage servers.**

### As a Full Stack Developer

A common serverless architecture is:

```
React
   │
API Gateway
   │
Lambda (Node.js)
   │
DynamoDB / RDS
```

This lets you build backend APIs **without using an EC2 server**.
