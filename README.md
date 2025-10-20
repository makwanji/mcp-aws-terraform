# Hands-On: Build AWS Resources with MCP Pipelines (Opt1)
# Modern Cloud Provisioning: MCP Meets GitHub Actions (Opt2)
# Automating AWS Resource Deployment with MCP Server & GitHub Actions ((Opt3)

## 🧭 Session Overview
In this session, we'll explore how **Model Context Protocol (MCP) Servers** integrate with **GitHub Actions** to automate infrastructure provisioning on **AWS Cloud**.
We'll walk through how MCP enables natural language–driven automation and how we can use **Copilot + MCP + Terraform** to spin up real cloud resources — all from **VS Code**.

---

# Table of Contents
1. [Introduction](#introduction)
2. [What is MCP Server](#what-is-mcp-server)
3. [Introduction to GitHub Actions](#introduction-to-github-actions)
4. [Demo Part 1 - Network Setup](#part-1---create-network-setup)
5. [Demo Part 2 - Create EKS](#part-2---create-eks-cluster)
6. [Demo Part 3 - Deploy App](#part-3---deploy-application)
7. [Summary](#summary)

---

## Introduction
Your intro content here...

[➡️ Next: What is MCP Server →](#what-is-mcp-server)

---

## What is MCP Server
MCP details...

[⬅️ Previous: Introduction](#introduction) | [➡️ Next: Introduction to GitHub Actions →](#introduction-to-github-actions)


## 🧩 What is MCP Server?

**MCP (Model Context Protocol)** is an open standard designed by OpenAI to connect AI models (like ChatGPT or GitHub Copilot) with external tools, data, and services in a secure and structured way.

### Key Concepts
- **MCP Server:** A local or remote service that exposes capabilities (APIs, data, or automation) that AI tools can use.
- **MCP Client:** The interface (e.g., ChatGPT, Copilot, VS Code) that communicates with the MCP Server.
- **Protocol Layer:** Ensures structured, secure interaction between AI and your environment.

### Why MCP?
- Enables **AI-driven automation** using existing DevOps tools.
- Standardizes integration between **LLMs and infrastructure-as-code** tools.
- Brings **context awareness** and **secure execution boundaries** to AI workflows.

---

## 🌱 Evolution of MCP Servers

| Stage | Description | Example |
|--------|--------------|---------|
| **v0.1 (Concept)** | AI tools could only talk via extensions or plugins. | ChatGPT Plugins |
| **v0.2 (Protocol)** | Introduction of MCP — structured protocol between AI and tools. | Early OpenAI MCP spec |
| **v1.0 (Server Ecosystem)** | Community and vendors start building MCP servers for CI/CD, IaC, Security. | `mcp-server-terraform`, `mcp-server-aws`, `mcp-server-github` |

---

## 🛠️ Introduction to `mcp-server-terraform`

**`mcp-server-terraform`** bridges AI tools and Terraform CLI.
It allows GitHub Copilot or ChatGPT (with MCP support) to:
- Create, plan, and apply Terraform configurations
- Generate `.tf` code on demand
- Manage state securely
- Automate infrastructure deployment workflows

### Benefits
- **Natural language IaC**: Ask Copilot to “create a VPC in AWS” and it writes Terraform code.
- **Reusable Environments**: MCP handles state and workspace setup.
- **Integration Ready**: Works well with GitHub Actions, VS Code, and local Terraform CLI.

---

## ⚙️ Introduction to GitHub Actions

**GitHub Actions** is a CI/CD platform to automate build, test, and deployment workflows directly from your GitHub repo.

### Why Combine MCP + GitHub Actions?
- MCP generates and manages Terraform code intelligently.
- GitHub Actions runs Terraform workflows securely on the cloud.
- Together, they form an **AI-Driven DevSecOps pipeline**.

Example Action:
```yaml
name: Deploy AWS Infra

on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: hashicorp/setup-terraform@v3
        with:
          terraform_version: 1.9.8
      - name: Terraform Init & Apply
        run: |
          terraform init
          terraform apply -auto-approve


## TODO
- mcp‑server‑terraform
- mcp‑server‑brave‑search
- mcp‑server‑docker

# Github Copilot
https://code.visualstudio.com/docs/copilot/overview

# Terraform
https://developer.hashicorp.com/terraform/mcp-server/deploy#run-in-docker
