# 🚀 Flask App Deployment on AWS ECS/Fargate | DevOps Project

---

## 📌 Project Overview
**Containerized** a Python Flask application using **Docker** and deployed it on **AWS ECS** with **Fargate** (serverless compute), demonstrating:
- **Containerization** best practices
- **CI/CD** pipeline fundamentals
- **Cloud Infrastructure** management
- **IaC** (Infrastructure as Code) concepts

---

## 📸 Step-by-Step Visual Walkthrough

### 1. Local Flask Application
![Local Flask App](screenshots/1-local-flask.png)  
*Flask app running locally at `localhost:5000`*

### 2. Docker Build Process
![Docker Build](screenshots/2-docker-build.png)  
*Building Docker image with successful output*

### 3. AWS ECR Repository
![ECR Repository](screenshots/3-ecr-repo.png)  
*Container image stored in Elastic Container Registry*

### 4. ECS Cluster Configuration
![ECS Cluster](screenshots/4-ecs-cluster.png)  
*ECS cluster dashboard showing running services*

### 5. Task Definition Setup
![Task Definition](screenshots/5-task-definition.png)  
*Fargate task configuration in AWS console*

### 6. Security Group Rules
![Security Group](screenshots/6-security-group.png)  
*Port 5000 open in inbound rules*

### 7. Running Service Details
![ECS Service](screenshots/7-ecs-service.png)  
*Service details showing healthy tasks*

### 8. Production Deployment
![Live Deployment](screenshots/8-live-app.png)  
*Final app accessible via public IP*

---

## 🛠️ Technologies Used
**Cloud Services**  
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
- ECS (Elastic Container Service)
- Fargate (Serverless Compute)
- ECR (Container Registry)
- IAM (Access Management)
- VPC (Networking)

**Tools**  
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)

---

## 📂 Project Setup

### Prerequisites
- AWS Account (Free Tier)
- AWS CLI configured (`aws configure`)
- Docker installed
- Python 3.9+

### Installation
---
# Clone repository
```bash
git clone https://github.com/git-hub-user7/flask-ecs-project.git
cd flask-ecs-project
```

# Install dependencies
```bash
pip install -r requirements.txt
```

# Build Docker image
```bash
docker build -t my-flask-app .
```
# Run locally
```bash
docker run -p 5000:5000 my-flask-app
```
☁️ AWS Deployment Steps
Create ECR Repository

```bash
aws ecr create-repository --repository-name my-flask-app
```
Push Docker Image to ECR

```bash
aws ecr get-login-password | docker login --username AWS --password-stdin <ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com

docker tag my-flask-app:latest <ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/my-flask-app:latest

docker push <ACCOUNT_ID>.dkr.ecr.<REGION>.amazonaws.com/my-flask-app:latest
```
Create ECS Cluster

```bash
aws ecs create-cluster --cluster-name my-app-cluster
```
Create Task Definition (Update ecs-task-def.json)

Configure Security Groups

Launch ECS Service

📚 Learning Outcomes
Containerized applications using Docker

Implemented cloud infrastructure on AWS

Configured IAM roles and security policies

Managed container orchestration with ECS

Practiced infrastructure-as-code principles

🤝 Connect with Me
Let's discuss cloud technologies and career opportunities!

📧 Email: dhwarakesh99@gmail.com
💼 LinkedIn: Dhwarakesh Srinivasan
📂 GitHub: git-hub-user7
