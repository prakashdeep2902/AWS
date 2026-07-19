**Amazon DynamoDB** is AWS's **fully managed NoSQL database service**.

### Simple Definition

Think of DynamoDB as a database that stores data as **key-value pairs** or **JSON-like documents**, and can handle **millions of requests per second** without you managing servers.

### Features

- ✅ NoSQL database
- ✅ Serverless (AWS manages everything)
- ✅ Very fast (single-digit millisecond latency)
- ✅ Automatically scales up/down
- ✅ Highly available across multiple Availability Zones

### Example

Suppose you're building an e-commerce app.

**Users Table**

| UserId (Primary Key) | Name    | Email                                         |
| -------------------- | ------- | --------------------------------------------- |
| 101                  | Prakash | [prakash@gmail.com](mailto:prakash@gmail.com) |
| 102                  | Rahul   | [rahul@gmail.com](mailto:rahul@gmail.com)     |

Here, `UserId` is the **Partition Key**.

You can quickly fetch a user:

```javascript
GetItem((UserId = 101));
```

### When to Use DynamoDB

Use it when your application needs:

- User sessions
- Shopping carts
- Gaming leaderboards
- Chat applications
- IoT data
- Real-time applications

### DynamoDB vs MySQL

| MySQL (RDS)                | DynamoDB                       |
| -------------------------- | ------------------------------ |
| SQL                        | NoSQL                          |
| Tables with fixed schema   | Flexible schema                |
| You manage database engine | AWS manages everything         |
| JOINs supported            | No JOINs                       |
| Best for relational data   | Best for massive scale & speed |

### Example in a Full Stack App

If you're building a MERN app:

- **Users** → DynamoDB
- **Products** → DynamoDB
- **Orders** → DynamoDB

Your Node.js backend can directly read/write data using the AWS SDK.

### As a Full Stack Developer

For most CRUD applications, you'll usually use:

- **Amazon RDS (MySQL/PostgreSQL)** if your data is relational.
- **Amazon DynamoDB** if you need high scalability, low latency, or flexible data models.

**Interview definition (1 line):**

> **Amazon DynamoDB is a fully managed, serverless NoSQL database service that provides fast, predictable performance with automatic scaling and high availability.**
