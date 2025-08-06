# 🌐 Day 11: VPC Monitoring with Flow Logs  
> **Track:** AWS Cloud Engineering  
> **Series:** #60DaysOfCloud by [NextWork](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)  
> **Author:** [Joba](https://www.linkedin.com/in/dvoice)

---

## 🚀 Project Overview

**Network visibility is non-negotiable** in any scalable and secure cloud architecture.

Today’s focus was on **VPC monitoring**—a key task for ensuring that your AWS infrastructure can be observed, secured, and optimized.

By implementing **VPC Flow Logs**, I enabled real-time visibility into both internal and external traffic flowing through peered VPCs. These insights are critical for validating connectivity, monitoring patterns, and identifying anomalies in AWS environments.

---

## 🛠️ What Was Built

- ✅ Deployed **two peered VPCs** with public subnets
- ✅ Enabled **VPC Flow Logs** to capture inbound and outbound traffic
- ✅ Sent flow logs to **Amazon CloudWatch Logs** for centralized visibility
- ✅ Used **CloudWatch Log Insights** to query and analyze traffic data
- ✅ Verified **bidirectional connectivity** using public and private IPv4 addresses

---

## 🧠 Why This Matters

For any cloud-native business or enterprise:

- **VPC Peering** enables secure, private communication between cloud resources
- **Flow Logs** help ensure that traffic is behaving as expected
- **CloudWatch** centralizes operational intelligence
- **Log Insights** allows DevOps and Security teams to detect anomalies or bottlenecks quickly

---

## 🔍 Use Cases & Problem Solving

- 🔐 **Security Audits:** Track unusual traffic patterns
- 🔄 **Connectivity Debugging:** Pinpoint routing issues between VPCs
- 📊 **Performance Tuning:** Understand load patterns and optimize architectures
- 🛑 **Compliance Monitoring:** Maintain logs for audits and security posture

---

## 🧰 Tools & Services Used

| Service                | Purpose                                         |
|------------------------|-------------------------------------------------|
| Amazon VPC             | Network segmentation                            |
| VPC Peering            | Private inter-VPC communication                 |
| VPC Flow Logs          | Traffic monitoring and log generation           |
| CloudWatch Logs        | Centralized logging                             |
| CloudWatch Log Insights| Real-time query engine for logs                 |
| EC2                    | Connectivity validation and traffic generation  |

---

## 📸 Screenshots & Documentation

📎 Attached:  
- `NextWork_Day11_VPC_Monitoring.md`  
- `NextWork_Day11_VPC_Monitoring.pdf`  

These files provide detailed step-by-step documentation including configuration details and insights gathered during the project.

---

## 📌 LinkedIn Post

> **Day 11 - Network visibility is non-negotiable in any scalable cloud architecture.**  
>  
> Today, I focused on monitoring traffic within and across VPCs using AWS-native tools.  
>  
> ✅ Established two peered VPCs with public subnets  
> ✅ Configured VPC Flow Logs  
> ✅ Directed flow data to CloudWatch  
> ✅ Queried traffic with Log Insights  
> ✅ Verified bidirectional traffic across both public and private IPv4 addresses  
>  
> This process enabled deeper visibility into network activity, highlighted key traffic patterns, and laid the foundation for better security posture and performance tuning.  
>  
> Thanks to @NextWork for the structure!  
>  
> 👉 [Connect with me on LinkedIn](https://www.linkedin.com/in/dvoice)  
>  
> 📚 [View full portfolio](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio)  

---

## 🔗 GitHub Repo

All my cloud engineering projects can be found in the [0xJoba/cloud-engineering-projects](https://github.com/0xJoba/cloud-engineering-projects) repository.

---

## 🧭 Next Steps

- Configure **VPC Flow Logs** for private subnets  
- Create CloudWatch **alarms** on suspicious traffic  
- Aggregate logs using **Athena** or **OpenSearch** for long-term analysis  
- Integrate **AWS Config** and **Security Hub** for compliance checks

---

## 🙌 Acknowledgments

Special thanks to the [NextWork](https://learn.nextwork.org/eager_lavender_swift_alligator/portfolio) team for curating real-world, job-relevant projects that push engineers to build **hands-on expertise**.

---

## 🔖 Tags

`#AWS` `#VPC` `#FlowLogs` `#CloudWatch` `#LogInsights` `#CloudNetworking` `#DevOps` `#CloudSecurity` `#Observability` `#NextWork` `#100DaysOfCloud` `#LearnInPublic`

