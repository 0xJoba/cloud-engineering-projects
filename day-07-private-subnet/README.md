# 🛡️ Day 7 — Creating a Private Subnet in AWS (Cloud Network Security)

One of the **biggest risks companies face in the cloud** is accidentally exposing critical infrastructure to the public internet. For Day 7 of my cloud journey, I tackled this risk directly by designing and deploying a **secure private subnet** in AWS.

## 🔧 What I Implemented

- **Created a Private Subnet**  
  Designed a subnet within a Virtual Private Cloud (VPC) meant for **internal workloads** like databases and backend services that should never be public-facing.

- **Configured a Custom Route Table**  
  Excluded any internet gateway to ensure **no inbound/outbound internet access**, reinforcing network isolation.

- **Applied Network Access Control List (ACL)**  
  Set default to **deny all traffic**. Then configured **explicit rules** to tightly control what’s allowed.

- **Enabled VPC Flow Logs**  
  Verified traffic flow and **monitored potential vulnerabilities or misconfigurations** using AWS logging.

## 🧠 Why This Matters

Security misconfigurations are a **leading cause of cloud data breaches**. This setup demonstrates:

- ✅ Principle of least privilege  
- ✅ Defense-in-depth at the network layer  
- ✅ A foundation for securing services in **regulated industries** like fintech or healthcare


---

## 🛠 Tools & Concepts Used

- AWS VPC  
- Private Subnet  
- Route Tables  
- Network ACLs  
- VPC Flow Logs  
- Cloud Security Best Practices

---

_This project is part of my hands-on cloud engineering journey, where I solve real-world problems and document my progress publicly._

🚶‍♀️ Walk with me.

