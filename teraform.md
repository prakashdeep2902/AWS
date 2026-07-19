## Terraform

**Terraform** is an **Infrastructure as Code (IaC)** tool developed by **HashiCorp**.

### Simple Definition

> **Terraform lets you create and manage AWS infrastructure using code instead of the AWS Console.**

---

## Without Terraform

You manually create:

- EC2
- VPC
- Subnets
- RDS
- Security Groups

using the AWS Console.

---

## With Terraform

You write a configuration file:

```hcl
resource "aws_instance" "web" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}
```

Run:

```bash
terraform init
terraform plan
terraform apply
```

Terraform creates the EC2 instance automatically.

---

## Why use Terraform?

- ✅ Infrastructure as Code (IaC)
- ✅ Automates AWS resource creation
- ✅ Easy to reuse and version-control
- ✅ Works with AWS, Azure, GCP, and more

---

## Example

```text
Terraform Code
       │
terraform apply
       │
       ▼
AWS
 ├── VPC
 ├── EC2
 ├── RDS
 └── S3
```

---

## Interview (1 line)

> **Terraform is an Infrastructure as Code (IaC) tool used to provision and manage cloud infrastructure through code.**

### Easy way to remember

- **CloudFormation** → AWS-only IaC tool.
- **Terraform** → Multi-cloud IaC tool (AWS, Azure, GCP, etc.).

Do you mean **"IaC (Infrastructure as Code)"** example in Terraform?

Here's a simple Terraform configuration that creates an EC2 instance:

```hcl
# Configure AWS Provider
provider "aws" {
  region = "ap-south-1"
}

# Create an EC2 Instance
resource "aws_instance" "web_server" {
  ami           = "ami-0f58b397bc5c1f2e8" # Example Amazon Linux AMI
  instance_type = "t2.micro"

  tags = {
    Name = "Terraform-EC2"
  }
}
```

Run these commands:

```bash
terraform init
terraform plan
terraform apply
```

Terraform will create the EC2 instance automatically.

If you meant something else by **"LOC"** (for example, "Lines of Code" or another term), let me know.
