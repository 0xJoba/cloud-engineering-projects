# Day 6 – VPC Traffic Flow and Security 🔐🌐

Understanding how traffic moves through your cloud infrastructure is fundamental to securing it. Today, I focused on controlling and observing **network traffic flow** within a VPC, and putting guardrails in place to protect cloud workloads.

---

## ✅ What I Configured

- Created **multiple subnets** in different Availability Zones
- Deployed **EC2 instances** in both public and private subnets
- Configured **Route Tables** to control internal routing
- Attached **Internet Gateway (IGW)** and **NAT Gateway** for outbound traffic
- Used **Security Groups** to allow specific access (e.g., SSH on port 22)
- Applied **Network ACLs** to control subnet-level traffic
- Verified **cross-subnet communication** and internet access using ping tests
- Used **VPC Flow Logs** to monitor network traffic and troubleshoot issues

---

## 🧠 Key Takeaways

- **Security Groups vs NACLs**: When to use which, and why
- The role of **NAT Gateways** in enabling secure outbound access for private instances
- How to **segment workloads** with public/private subnets for tighter control
- Reading **VPC Flow Logs** to detect anomalies or verify access patterns

This project pushed me to think like a **cloud network architect**, balancing access and security for real-world cloud deployments.

---

## 🛠️ Tools & Services

- Amazon VPC
- EC2
- Route Tables
- NAT Gateway
- Internet Gateway
- VPC Flow Logs
- Security Groups & NACLs

---

 

---

This is more than theory — this is about architecting resilient, secure, and scalable networks in the cloud.

> – Joba  
> [LinkedIn](https://www.linkedin.com/in/dvoice) | [GitHub](https://github.com/0xjoba)

---

#AWS #VPC #CloudSecurity #NetworkArchitecture #NextWork #LearningInPublic #BuildInPublic #CloudEngineering
