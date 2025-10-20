# 3️⃣ Introduction to GitHub Actions

**GitHub Actions** is a powerful CI/CD platform built into GitHub that automates your workflows — from code commits to deployment.

---

## 🚀 What GitHub Actions Does
- Automates build, test, and deploy pipelines.
- Runs directly from your repository.
- Uses YAML-based workflow definitions.
- Supports environment secrets and reusable workflows.

---

## 🤝 Why Combine MCP + GitHub Actions
| Feature | MCP Server | GitHub Actions | Together |
|----------|-------------|----------------|-----------|
| Intelligence | AI-driven IaC generation | Automated CI/CD execution | Smart, continuous automation |
| Context | Accesses Terraform & local setup | Executes workflows in cloud runners | Seamless local-to-cloud integration |
| Governance | Scoped via MCP security model | Managed via GitHub Secrets | Secure IaC automation pipeline |

---

## ⚙️ Example GitHub Action Workflow

```yaml
name: Deploy AWS Infra

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v4

      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v3
        with:
          terraform_version: 1.9.8

      - na
