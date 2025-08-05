# 🔗 Day 10 — VPC Peering in AWS

Today, I took a step deeper into cross-network communication by configuring **VPC Peering** between two Virtual Private Clouds. This is crucial for organizations operating multiple isolated environments that still need to talk to each other securely — without going over the public internet.

---

## ✅ What I Did

- **Created a Peering Connection**
  - Established a secure peering link between two VPCs in the same region
  - One VPC hosted a public-facing workload, while the other contained private internal services

- **Updated Route Tables**
  - Enabled bidirectional routing between peered VPCs
  - Carefully scoped traffic to avoid accidental exposure

- **Verified Peering Connectivity**
  - Used private IPs to ping resources across the peered networks
  - Ensured no dependency on NAT Gateways or Internet Gateways

---

## 🔒 Why VPC Peering Matters

VPC Peering allows **private, low-latency, and secure communication** between cloud environments — essential for:

- Microservices that span across teams or departments
- Shared internal tooling (e.g., logging, databases, APIs)
- Multi-account or multi-VPC strategies for better governance

No need for VPNs, no single points of failure, and no public internet in the middle.

---

## 🛠️ Tools & Concepts Used

- AWS VPC Peering
- Custom Route Tables
- Private IP Connectivity
- Security Group Tweaks

Still learning. Still building. Walk with me.
