# -EC2-Auto-Deployment-with-User-Data
This project demonstrates how to **automatically deploy an Apache web server** on an EC2 instance using **User Data** during instance launch. It also includes setting up **security groups** to allow HTTP and SSH access.

# 🚀 EC2 Auto Deployment with Auto Scaling & Load Balancer (AWS CloudFormation)

This project demonstrates how to automatically deploy an Apache web server using **EC2 instances**, **User Data scripts**, and AWS **Auto Scaling Groups (ASG)** behind an **Application Load Balancer (ALB)** — all provisioned using **AWS CloudFormation**.

## 📌 Project Goals

- Automatically install Apache and serve a "Hello World" web page on EC2.
- Automatically launch EC2 instances via an Auto Scaling Group.
- Distribute traffic across instances using an Application Load Balancer.
- Parameterize AMI ID and instance type for flexibility.
- Allow access only through HTTP and SSH with security best practices.

---

📝 User Data Script (user-data.sh)  -   
bash 
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from EC2!</h1>" > /var/www/html/index.html



## 🧰 Key AWS Services Used

- **EC2 (Elastic Compute Cloud)**
- **Auto Scaling Group**
- **Application Load Balancer (ALB)**
- **Security Groups**
- **Launch Templates**
- **CloudFormation**

---

## 🛠️ How It Works

- **Launch Template** provisions EC2 instances with Apache pre-installed using User Data.
- **Security Groups**:
  - Allow HTTP (80) from ALB to EC2 instances.
  - Allow SSH (22) from anywhere (can be restricted).
  - ALB allows HTTP (80) from public internet.
- **Auto Scaling Group (ASG)** ensures 1–2 EC2 instances are always available.
- **ALB** balances traffic to healthy EC2 instances.
- A simple web page is rendered with the message and instance's public IP.

---




