
---

### 🧱 **04-demo-part1.md**
```markdown
# 4️⃣ Demo Part 1 — Create Network Setup

In this first demo, we'll use **VS Code**, **Copilot**, and **mcp-server-terraform** to create a foundational AWS network.

---

## 🎯 Goal
Provision a **VPC**, **subnets**, and **Internet Gateway** — ready for EKS and apps.

---

## 🧰 Prerequisites
- VS Code with MCP extension installed
- `mcp-server-terraform` configured and connected
- AWS credentials available (`~/.aws/credentials`)
- Terraform CLI installed

---

## 💬 Ask Copilot

> “Create Terraform code for a VPC with 2 public and 2 private subnets in `us-east-1`, along with route tables and an Internet Gateway.”

Example Terraform snippet Copilot might generate:
```hcl
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "public_a" {
  vpc_id     = aws_vpc.main.id
  cidr_block = "10.0.1.0/24"
  map_public_ip_on_launch = true
  availability_zone = "us-east-1a"
}
