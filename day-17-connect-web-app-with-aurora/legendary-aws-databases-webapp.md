<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a Web App with Aurora

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-webapp)

**Author:** Joba Amunigun  
**Email:** jobaamunigun@gmail.com

---

## Connect a Web App to Amazon Aurora

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-databases-webapp_1709b26b)

---

## Introducing Today's Project!

### What is Amazon Aurora?

Amazon Aurora is a fully managed relational database engine offered by AWS that is compatible with MySQL and PostgreSQL. It combines the speed and reliability of high-end commercial databases with the simplicity and cost-effectiveness of open-source databases.

Aurora is useful because it automatically handles time-consuming tasks like provisioning, patching, backup, recovery, and failover, allowing developers to focus on building applications. It’s highly scalable, fault-tolerant, and offers better performance than standard MySQL—with up to 5x faster throughput—making it ideal for modern cloud-based applications.

### How I used Amazon Aurora in this project

n today's project, I used Amazon Aurora to create a highly available, MySQL-compatible relational database cluster. I connected it to an EC2 instance that acted as a web server, enabling my web app to store and retrieve employee data in real time. Aurora’s scalability and built-in failover features made it a reliable choice for handling database operations securely and efficiently in the cloud. 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how many permissions and ownership settings I needed to adjust manually in the EC2 instance just to create and modify files. It really showed me how important user roles and security are when managing servers in AWS.




### This project took me...

 This project took me approximately 3–4 hours to complete. That included setting up the Aurora database, configuring the EC2 instance, troubleshooting permissions, and verifying everything worked together seamlessly.

---

## Creating a Web App

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-databases-webapp_b7999168)

To connect to my EC2 instance, I first located my ".pem" key file (NextWorkAuroraApp.pem) and moved it into a dedicated nextwork folder on my Desktop for easy access. Using the terminal, I navigated into this folder by running "cd Desktop/nextwork" and confirmed the key file was present using the ls command.

Before connecting, I updated the file permissions using "chmod 400 NextWorkAuroraApp.pem" to ensure it was secure and accessible only by me, as required by AWS SSH standards. I then successfully established a secure connection to my EC2 instance using the SSH command:"ssh -i NextWorkAuroraApp.pem ec2-user@ec2-18-221-61-181.us-east-2.compute.amazonaws.com"

This allowed me to remotely access the EC2 instance's terminal environment from my local machine.

 

To help me create my web app, I ran the following commands on my WINDOWS Powershell (After connecting to my EC2 instance through SSH)
"sudo dnf update -y" ,"sudo dnf install -y httpd php php-mysqli mariadb105" , and "sudo systemctl start httpd
"
Here’s what each component does:

httpd: Installs and starts the Apache web server, which delivers web pages to users.

php: Installs PHP, the language used to write server-side web logic.

php-mysqli: Adds MySQL support to PHP so it can talk to my Aurora database.

mariadb105: Installs the MariaDB client, a MySQL-compatible tool to let EC2 communicate with the database.

After installation, I tested the setup by visiting my EC2 instance’s public DNS in the browser:"http://ec2-18-221-61-181.us-east-2.compute.amazonaws.com"

This confirmed that my web server was running and ready to connect to the database. (It Works!)





---

## Connecting my Web App to Aurora

To connect my EC2 instance to my Aurora database, I:

Navigated to the EC2 web directory at /var/www and changed its ownership using sudo chown ec2-user:ec2-user /var/www to gain the necessary permissions for creating and modifying files.

Created a new subfolder named inc to store configuration files, then navigated into it using cd inc.

Created a configuration file named dbinfo.inc to securely store

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-databases-webapp_1709b25b)

---

## My Web App Upgrade

To upgrade my web app and connect it to my Aurora database, I:

Navigated to the EC2 web root directory at /var/www/html, where all public-facing website files are stored.

Created a new PHP file called SamplePage.php using the nano text editor.

Wrote a dynamic PHP script that:

Connected to my Aurora database using the credentials stored in dbinfo.inc

Created an EMPLOYEES table if it didn’t already exist

Allowed users to add employee data

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-databases-webapp_2709b25b)

---

## Testing my Web App

 To make sure my web app was working correctly, I:

✅ Installed the MySQL CLI on my EC2 instance to directly interact with my Aurora MySQL database.
✅ Connected to the Aurora Writer instance using the MySQL command:
mysql -h nextwork-db-cluster-instance-1.c3oy8cw0egrr.us-east-2.rds.amazonaws.com -P 3306 -u admin -p
✅ Logged in and ran the following SQL commands to inspect the data:

SHOW DATABASES; – to confirm that the sample database

![Image](http://learn.nextwork.org/eager_lavender_swift_alligator/uploads/aws-databases-webapp_1409z22b)

---

---
