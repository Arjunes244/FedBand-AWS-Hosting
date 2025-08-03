# FedBank Project Deployment on AWS

## 🌐 Project Overview

This repository documents the end-to-end deployment of the Django-based **FedBank** web application on AWS infrastructure. The **application was developed by Rohit Remesh**, while the **hosting, deployment, and AWS configuration were carried out by Arjun E S**.

---

## 👨‍💻 Project Contributors

- **Application Developer:** Rohit Remesh
- **DevOps & Deployment Engineer:** Arjun E S

---

## 🛠️ Technologies Used

- **Cloud Platform:** Amazon Web Services (AWS)
- **Web Framework:** Django (Python)
- **Web Servers:**
  - Nginx (for static file serving)
  - Gunicorn (WSGI server for Django app)
  - Apache2 (used in test environments)
- **Database:** MySQL (deployed in a private subnet)
- **Operating System:** Ubuntu Server

---

## 🏗️ AWS Infrastructure Details

### VPC & Networking

- Created a custom VPC with both public and private subnets
- Properly configured route tables and subnet associations
- Set up an Internet Gateway and a NAT Gateway for internet access

### EC2 Instances

- **Application Server:** Private subnet, runs Django app with Gunicorn
- **Static Server:** Public subnet, serves static files using Nginx
- **Database Server:** Private subnet, hosts MySQL

### Load Balancer

- Application Load Balancer (ALB) created
- Target group includes the EC2 instance running the Django application
- Health checks configured for target group monitoring

### Domain & SSL

- **Domain:** `fedbank.arjunes.online`
- Hosted zone managed in Amazon Route 53
- SSL certificate issued via AWS Certificate Manager (ACM) and attached to the ALB for HTTPS

### Auto Scaling

- Launch Template created using the application EC2 instance
- Auto Scaling Group (ASG) configured with:
  - **Minimum Capacity:** 1 instance
  - **Maximum Capacity:** 3 instances
  - **Target Group:** Connected to ALB

---

## ✅ Key Features Completed

- Django application deployed and accessible via HTTPS through ALB
- Static content served efficiently through a dedicated Nginx EC2 instance
- Domain successfully configured and SSL secured using ACM
- Auto Scaling verified under simulated load

---

## 📜 License

This repository includes only the deployment and infrastructure setup. It is intended for educational and demonstration purposes only.

