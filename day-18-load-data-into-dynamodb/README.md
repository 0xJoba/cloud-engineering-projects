# 📊 Day 18: Load Data into DynamoDB
**NextWork Cloud Engineering Journey**

Ever wondered how **DynamoDB handles data** compared to traditional relational databases?  
This week, I dove into a hands-on project that gave me a deeper understanding of **NoSQL structures** and why they shine in production environments.

---

## 🔍 The Challenge
- Load structured data into a **NoSQL table**  
- Perform updates at the **attribute level**  
- Optimize for **speed, flexibility, and scalability**  

---

## 🛠️ Step-by-Step Solution
1. **Create a DynamoDB Table**
   - Defined partition key and optional sort key  
   - Selected on-demand or provisioned throughput based on test needs  

2. **Load Data Using AWS CloudShell**
   - Used `aws dynamodb put-item` and `batch-write-item` commands  
   - Imported JSON data for multiple items efficiently  

3. **Attribute-Level Updates**
   - Performed updates using `update-item` commands  
   - Verified successful updates and consistency across the table  

4. **Test and Validate**
   - Queried the table using `scan` and `query` commands  
   - Confirmed low-latency responses and flexible data access  

---

## ✅ Outcome
- Fully functional **NoSQL table** optimized for fast access and scalability  
- Clear understanding of **DynamoDB's advantages over relational databases**  
- Hands-on experience performing CRUD operations in AWS-managed NoSQL  

---

## 🛠 Tools Used
- **Amazon DynamoDB**  
- **AWS CloudShell**  
- **JSON Data Files**  

---

## 📥 Documentation
Step-by-step guide with commands, screenshots, and table configuration details is available:  
 
---

**#AWS #CloudComputing #DynamoDB #NoSQL #TechLearning #LearnInPublic #NextWork**
