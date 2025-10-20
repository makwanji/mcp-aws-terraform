
---

### ☸️ **05-demo-part2.md**
```markdown
# 5️⃣ Demo Part 2 — Create EKS Cluster

Now that the network is ready, we’ll create an **Amazon EKS cluster** and its node groups using `mcp-server-terraform`.

---

## 🎯 Goal
Deploy a fully working **EKS cluster** inside the VPC created earlier.

---

## 💬 Ask Copilot
> “Using `mcp-server-terraform`, create Terraform code for an EKS cluster using the existing VPC and subnets.”

Expected Terraform output (simplified):
```hcl
module "eks" {
  source          = "terraform-aws-modules/eks/aws"
  cluster_name    = "demo-eks"
  vpc_id          = aws_vpc.main.id
  subnet_ids      = [aws_subnet.public_a.id, aws_subnet.public_b.id]
  cluster_version = "1.31"
}
