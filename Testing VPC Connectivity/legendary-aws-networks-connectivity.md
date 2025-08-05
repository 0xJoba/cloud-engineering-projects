<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** Joba Amunigun  
**Email:** jobaamunigun@gmail.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a private, isolated section of the AWS cloud where I can launch and manage resources like EC2 instances, databases, and load balancers in a secure network environment.

It’s useful because it gives me full control over my network — including IP addresses, subnets, route tables, internet gateways, and security settings. This means I can design how traffic flows, decide what stays private, and protect resources from unwanted access.

 Think of it as building your own private neighborhood in the cloud — with custom roads, gates, and guards.

### How I used Amazon VPC in this project

In today’s project, I used Amazon VPC to test connectivity between two EC2 instances — one in a public subnet and one in a private subnet.

I configured:

- Route tables to control traffic flow

- Network ACLs and Security Groups to manage access

- An Internet Gateway to enable external communication for the public server

Then, I used tools like ping and curl to verify that the public server could:

- Talk to the private server within the VPC

- Reach the internet successfully

  It was all about ensuring that the right traffic was flowing in and out — securely and intentionally.

### One thing I didn't expect in this project was...

One thing I didn’t expect was how one missing rule in a Network ACL or Security Group could completely block communication — even when everything else looked correctly configured.

I had assumed my route tables and public subnet setup were enough, but I learned that fine-tuning permissions at multiple layers (like allowing ICMP or SSH) is essential for proper connectivity.

### This project took me...

This project took me a little over 1 hour — including time spent testing connectivity, troubleshooting blocked ping requests, and adjusting Network ACLs and Security Groups to get everything working smoothly.

---

## Connecting to an EC2 Instance

Connectivity means how well different parts of a network can communicate with each other and the outside world.
It's essential because connectivity is how data flows smoothly across your network, powering everything from simple web hosting on the Internet to complex operations e.g. Netflix using over 100,000 EC2 instances to power its streaming platform.

In cloud networking, this includes making sure your EC2 instances, subnets, route tables, and security settings all work together so data can flow where it needs to go — securely and efficiently.

My first connectivity test was whether I could connect to NextWork Public Server but I got an error stating 
"Failed to connect to your instance"

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a shortcut way to get direct SSH access to my EC2 instance!

It's an alternative way to use SSH — it lets you securely connect to your EC2 instances directly using the AWS Management Console. You're still using SSH, but with all the key management handled for you. This takes away a lot of the complexity of setting up SSH.

My first attempt at getting direct access to my public server resulted in an error, because after investigating by reviewing my Security settings ( I.e. Subnet - Network ACL and Route tabs) and everything looked good (My Network ACL allows all traffic in and out, and my route table is correctly setting up a route to the Internet Gateway)
So i had to review the security groups and realised that The security group associated with NextWork Public Server lets in all inbound HTTP traffic, but this is not how i was trying to access my Public Server!

I am trying to access NextWork Public Server using SSH through EC2 Instance Connect, which is a different traffic type.

I fixed this error by updating NextWork Public Server's security group to allow SSH traffic.

I added a new inbound rule for SSH (port 22) and set the source to Anywhere-IPv4, which lets SSH connections come from any IPv4 address.

  P.S. While this worked for testing, it's not best practice to allow SSH from "Anywhere-IPv4" long-term — it can expose your server to security risks. A better approach is to restrict access to specific IPs.

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a common computer network tool used to check whether your computer can communicate with another computer or device on a network.

Think of it like sending a tiny message that says "hello, are you there?" to another computer, or like checking if someone's home by ringing their doorbell.

When you "ping" a specific IP address address (i.e. another server's address), your server (in this case, NextWork Public Server) sends a small packet of data to that address (NextWork Private Server), asking for a response. Ping will tell you whether you get a response back and how long it took to get a response.

If you receive a response quickly, it means the connection between your computer and the other computer is good. If it takes a long time or you get no response, there might be a problem with the connection! 

In this case I used ping to test the connectivity between my NextWork Public Server and Nextwork Private Server

The ping command I ran was  "ping 10.0.1.103"

The first ping returned a single line this meant that  my Public Server has sent out a ping message - and that's about it (There is no response)

- Usually, when you ping another computer successfully, you should see several replies back instantly. Each reply tells you how long it took for the message to go to the Private Server and come back.

If you don't get any replies (which is the situation right now), or if the replies stop suddenly, it's usually a sign that there's a problem with the connection. 



![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by reviewing both the Network ACL and Security Group settings for my NextWork Private Server.

While my route table was correct, I found that the Network ACL denied all inbound and outbound traffic, including ICMP (ping) messages. I fixed this by:

✅ Updating the Network ACL to allow All ICMP - IPv4 from my public subnet (10.0.0.0/24)
✅ Editing the Private Security Group to allow ICMP traffic from the NextWork Public Security Group

Once both layers were adjusted, I successfully received ping replies — confirming the instances could communicate.



![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a command-line tool used to test connectivity and transfer data between your machine and a server.

While ping checks if one device can reach another, curl goes further — it actually sends a request (like HTTP) and retrieves data from the server. When I ran curl nextwork.org, it sent an HTTP request to the server, and the raw HTML response was displayed in my terminal.

This confirmed that my public server could successfully talk to the internet — and that my subnet, internet gateway, and security settings were working just right.



I used curl to test the connectivity between my NextWork Public Server and the internet — and to confirm that it could send and receive data from external websites.

When I ran "curl nextwork.org" - I received a Found response. This meant the site had redirected to a new URL — which is accurate, since NextWork now redirects to its project page. I then followed that redirect and ran:

"curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3"

 This time, I got a large chunk of raw HTML data, showing that the public server successfully fetched the full contents of a live webpage — proving that my internet gateway, public subnet, and security group were all configured correctly.

### Ping vs Curl

Ping and curl are different because they test different types of connectivity.

**Ping** checks if two machines can reach each other on a network. It sends small packets and waits for a reply, showing you basic network reachability and latency.

**Curl** goes a step further — it not only checks connection but also sends and receives actual data (like HTML from a website) using protocols like HTTP or HTTPS.

 - Think of ping as “Are you there?” and curl as “Can you send me the actual stuff you have?”

---

## Connectivity to the Internet

I ran the curl command:
 "curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3"

which returned the full HTML content of the page — confirming that my public EC2 instance could successfully reach the internet and retrieve live web data.

 This response showed me that all networking components — subnet, internet gateway, route table, and security group — were working together correctly.

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-networks-connectivity_8ee57662)

---

---
