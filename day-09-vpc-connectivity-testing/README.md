# 🔌 Day 9 — Testing VPC Connectivity

After deploying our VPC and launching instances across public and private subnets, today was all about **testing and verifying network connectivity** — the key to ensuring that our architecture behaves exactly as designed.

---

## ✅ What I Did

- **SSH into Public EC2 Instance**
  - Verified internet access via the Internet Gateway
  - Acted as a bastion to access private resources

- **Connected to Private EC2 Instance**
  - Jumped through the bastion (public EC2) using SSH agent forwarding
  - Confirmed no direct internet access from the private subnet

- **Validated Route Tables and NACLs**
  - Ensured route tables correctly directed traffic to/from NAT and Internet Gateways
  - Confirmed NACL rules blocked unintended access

- **Tested Inbound & Outbound Traffic**
  - Used `ping`, `curl`, and traceroute to test communication paths
  - Ensured private instances could reach the internet via NAT Gateway (but not be reached)

---

## 🚧 Why This Step Matters

You don’t just build infrastructure — you **verify** it.

Testing VPC connectivity ensures:

- 🔒 Private resources stay isolated and secure
- 📶 Public-facing services are reachable and functional
- 🧪 All network control rules (SGs, NACLs, route tables) behave as expected

Skipping this step can lead to **downtime**, **data exposure**, or **blocked services** in production.

---

## 🛠️ Tools & Commands Used

- SSH (with key pair and agent forwarding)
- `ping`, `curl`, `traceroute`, `telnet`
- AWS Console & VPC Flow Logs


Still building. Still early. Walk with me.
