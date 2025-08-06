# 🔒 Day 13: Keeping AWS Traffic Secure with VPC Endpoints  
> **Track:** AWS Cloud Engineering  
> **Series:** #60DaysOfCloud by [NextWork](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)  
> **Author:** [Joba](https://www.linkedin.com/in/dvoice)

---

## 🧭 Project Overview

In cloud architecture, minimizing exposure to the **public internet** is key to building secure and efficient systems.

This project explores how to use **VPC Endpoints** to establish private connectivity between a VPC and AWS services like **Amazon S3**, without routing traffic over the internet — improving both **security** and **latency**.

---

## 🛠️ What I Implemented

- ✅ Deployed a **custom VPC** with a **public subnet** and an **EC2 instance**
- ✅ Created a **VPC Gateway Endpoint** to enable private access to **Amazon S3**
- ✅ Configured a **bucket policy** to allow access **only via the VPC Endpoint**
- ✅ Updated **route tables** to direct S3-bound traffic through the endpoint
- ✅ Validated the setup by running **AWS CLI commands** from the EC2 instance
  - No internet access was required to interact with the S3 bucket!

---

## 🧩 Problem Solved

Many organizations need to interact with AWS services like S3 or DynamoDB **without sending sensitive data over the public internet**.

This project addresses:
- **Private connectivity** between EC2 and S3
- **Restricted access control** via endpoint-specific bucket policies
- **Improved network security posture** by avoiding public gateways

---

## 🧰 Tools & Services Used

| Service             | Purpose                                     |
|---------------------|---------------------------------------------|
| Amazon VPC          | Network isolation and routing               |
| EC2                 | Compute environment for validation          |
| S3                  | Cloud storage accessed privately            |
| VPC Gateway Endpoint| Private access to S3 from VPC               |
| IAM & Bucket Policy | Enforce access restrictions                 |
| AWS CLI             | Programmatic access to validate setup       |

---

## 💡 Key Concepts Reinforced

- **VPC Endpoint architecture** and types (Gateway vs Interface)
- **Secure access patterns** in cloud-native environments
- **IAM policies and resource-level access control**
- **Routing configurations** to support endpoint traffic
- **CLI-driven validation** of real-world use cases

---

## 📎 Attached Files

- `NextWork_Day14_VPC_Endpoints.md`
- `NextWork_Day14_VPC_Endpoints.pdf`

Detailed instructions, configuration screenshots, and AWS CLI command outputs are included in the documentation.

---

## 📢 LinkedIn Summary

> **Day 13 – Keeping AWS Traffic Secure with VPC Endpoints**  
>  
> Today I implemented a secure AWS architecture where EC2 could access S3 *without touching the public internet*, using a VPC Gateway Endpoint.  
>  
> This is exactly how production teams protect sensitive data flows and reduce attack surfaces.  
>  
> Thanks @NextWork for guiding this hands-on project!  
>  
> 👉 [Connect on LinkedIn](https://www.linkedin.com/in/dvoice)  
> 🧠 [Full portfolio](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)

---

## 🔗 GitHub Repository

Explore all my AWS projects here:  
🔗 [0xJoba/cloud-engineering-projects](https://github.com/0xJoba/cloud-engineering-projects)

---

## 🚀 Next Steps

- Explore **Interface Endpoints** for services like SSM or Secrets Manager  
- Use **Endpoint policies** to restrict specific service actions  
- Automate this setup using **Infrastructure as Code (IaC)**

---

## 🔖 Tags

`#AWS` `#CloudSecurity` `#AmazonVPC` `#VPCGateway` `#AWSNetworking` `#S3` `#PrivateAccess` `#NextWork` `#CloudComputing` `#DevOps` `#LearningInPublic`
