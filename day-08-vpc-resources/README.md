# 🚀 Day 8 — Launching EC2 Instances Inside a Custom VPC

Today’s focus was deploying **compute resources** in a **custom Virtual Private Cloud (VPC)** designed for **isolation, control, and scalable architecture**.

This wasn’t just about launching EC2s — it was about building a secure foundation that mirrors real-world enterprise infrastructure.

---

## ✅ What I Deployed

- **Public EC2 Instance**
  - Launched with key pair authentication
  - Accessible from the internet for outward-facing workloads

- **Private EC2 Instance**
  - Launched inside an isolated subnet
  - Only reachable through the public instance (via SSH or bastion)

- **Security Groups & Network ACLs**
  - Directional rules for traffic control
  - Inbound and outbound access tightly restricted

- **VPC Resource Map**
  - Used to visually deploy and link subnets, route tables, and internet/NAT gateways
  - Improved visibility and modularity of VPC components

---

## 🌐 Why This Matters

Every decision here was made through a **production lens**:

- 🔐 Can this setup reduce risk for live workloads?
- 📉 Does this lower cloud costs by minimizing exposed services?
- 📈 Is the architecture scalable and modular for future growth?

The goal wasn’t just deployment — it was **learning how to think like a cloud engineer** designing systems that work under pressure.


## 🧰 Tools & Services Used

- AWS EC2
- Amazon VPC
- Subnets (Public & Private)
- Internet Gateway & NAT Gateway
- Route Tables
- Security Groups
- Network ACLs

---

Project by project -

🚶‍♀️ Still early. Walk with me.

