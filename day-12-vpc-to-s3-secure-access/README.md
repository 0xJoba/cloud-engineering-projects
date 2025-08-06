# 🔐 Day 12: Architecting Secure Access Between VPC and S3  
> **Track:** AWS Cloud Engineering  
> **Series:** #60DaysOfCloud by [NextWork](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)  
> **Author:** [Joba](https://www.linkedin.com/in/dvoice)

---

## 🧭 Project Overview

In modern cloud environments, enabling communication between compute resources (like EC2) and storage services (like S3)—**without exposing them to the public internet**—is a critical challenge that directly affects data security, compliance, and operational integrity.

This project focused on implementing **secure, private access** from an EC2 instance within a VPC to Amazon S3 using IAM credentials and the AWS CLI.

---

## 🛠️ What I Did

- ✅ Provisioned a **custom VPC** with subnet, route table, and an **EC2 instance**
- ✅ Created a **private S3 bucket** with restricted access
- ✅ Generated **IAM programmatic access credentials**
- ✅ Used the **AWS CLI** on the EC2 instance to:
  - List objects in the S3 bucket
  - Upload a test file to verify access

---

## 🔍 Problem Solved

In production, companies often need to move files between applications and object storage (e.g., backups, logs, datasets) **without exposing S3 buckets or EC2 instances to public networks**.

This solution demonstrates:
- How to isolate EC2 instances inside a secure VPC
- How to configure **least-privilege access** using IAM
- How to interact with S3 through **CLI commands**, mirroring real-world automation scripts and pipelines

---

## 🧰 Tools & Services Used

| Service         | Purpose                                  |
|-----------------|-------------------------------------------|
| Amazon VPC      | Private network isolation                 |
| EC2             | Compute instance within a private subnet  |
| Amazon S3       | Secure storage for cloud data             |
| IAM             | Credential-based access control           |
| AWS CLI         | Programmatic access for uploads/listing   |

---

## 🧠 Key Concepts Reinforced

- **Network isolation** via custom VPC and subnets
- **IAM-based authentication** using access keys
- **Programmatic interaction** with AWS services using CLI
- **Security best practices** in handling access to storage systems

---

## 📎 Attached Files

- `NextWork_Day12_S3_Access_From_VPC.md`
- `NextWork_Day12_S3_Access_From_VPC.pdf`

These documents include configuration steps, IAM permissions, CLI commands, and verification screenshots.

---

## 📢 LinkedIn Summary

> **Day 12 – Architecting Secure Access Between VPC and S3**  
>  
> In modern cloud environments, enabling communication between compute and storage services—without exposing them to the public internet—is a critical challenge.  
>  
> Today, I solved that by provisioning a custom VPC and connecting an EC2 instance to a private S3 bucket using IAM credentials and the AWS CLI.  
>  
> This is how real teams build secure data pipelines, internal tools, and backup workflows.  
>  
> Thanks @NextWork for guiding this hands-on journey.  
>  
> 👉 [Connect with me on LinkedIn](https://www.linkedin.com/in/dvoice)  
> 📚 [View full portfolio](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)

---

## 🔗 GitHub Repository

Explore all cloud engineering projects in the main repo:  
🔗 [0xJoba/cloud-engineering-projects](https://github.com/0xJoba/cloud-engineering-projects)

---

## 🏁 What’s Next?

- Use **Instance Roles** instead of access keys for tighter security  
- Connect via **VPC Endpoints** instead of public routing  
- Apply **bucket policies** for conditional access  
- Automate access and upload workflows using **Bash scripts** or **Terraform**

---

## 🔖 Tags

`#AWS` `#VPC` `#AmazonS3` `#IAM` `#EC2` `#CloudSecurity` `#AWSCLI` `#CloudInfrastructure` `#NextWork` `#DevOps` `#Networking` `#InfrastructureAsCode` `#LearningInPublic`
