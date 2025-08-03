# 🚀 FedBank Project Deployment on AWS

## 🌐 Project Overview

This repository provides a comprehensive walkthrough of deploying the Django-based **FedBank** web application on AWS infrastructure. The **application was developed by Rohit Remesh**, while **Arjun E S** was responsible for the complete **hosting, deployment, and AWS infrastructure setup**.

---

## 👥 Project Contributors

- **Application Developer:** Rohit Remesh
- **DevOps & Cloud Deployment Engineer:** Arjun E S

---

## 🛠️ Technologies Used

- **Cloud Provider:** Amazon Web Services (AWS)
- **Framework:** Django (Python)
- **Web Servers:**
  - **Gunicorn** – WSGI server for serving Django application
  - **Nginx** – Used for static file hosting
  - **Apache2** – Utilized in early test environments
- **Database:** MySQL (hosted in private subnet)
- **Operating System:** Ubuntu Server (EC2 instances)

---

## 🏗️ AWS Infrastructure Architecture

### 🕸️ VPC & Networking

- Custom Virtual Private Cloud (VPC) with isolated **public** and **private** subnets
- Configured route tables, NAT Gateway, and Internet Gateway
- Ensured secure traffic flow across tiers with subnet association and routing

### 🖥️ EC2 Instances

- **Application Server:** Located in a private subnet; runs Django with Gunicorn
- **Static File Server:** Located in a public subnet; serves static files via Nginx
- **Database Server:** MySQL hosted in a private subnet for security

### ⚖️ Load Balancer

- Created an **Application Load Balancer (ALB)**
- Integrated with a **Target Group** containing the Django application EC2 instance
- Configured **health checks** for seamless traffic routing

### 🌍 Domain & SSL

- **Domain Name:** `fedbank.arjunes.online`
- DNS managed via **Amazon Route 53**
- **SSL Certificate** provisioned using **AWS Certificate Manager (ACM)**
- SSL integrated with ALB for secure HTTPS access

### 📈 Auto Scaling

- Created a **Launch Template** from the application EC2 instance
- Configured an **Auto Scaling Group (ASG)** with the following settings:
  - **Min Instances:** 1
  - **Max Instances:** 3
  - **Target Group:** Connected to the ALB
- Simulated traffic tested to validate Auto Scaling behavior

---

## ✅ Key Accomplishments

- ✅ Deployed and hosted Django web application using EC2 and ALB
- ✅ Configured static file delivery via Nginx on a separate instance
- ✅ Enabled secure HTTPS access with a custom domain and ACM SSL certificate
- ✅ Verified Auto Scaling functionality under load simulation

---

## 🖼️ Screenshot

<img width="1848" height="1003" alt="image" src="https://github.com/user-attachments/assets/75a5aab3-7da1-4ed8-80dd-897f7778474c" />


---

## 📜 License

This repository focuses solely on the **deployment and infrastructure configuration**. The content is shared for **educational and demonstration purposes only**.

