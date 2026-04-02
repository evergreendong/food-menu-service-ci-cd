# 🚀 Automated CI/CD Pipeline for Containerized Applications on AWS

## 📌 Overview

This project demonstrates a **production-ready CI/CD pipeline** using GitHub Actions and AWS services.

A Dockerized Node.js application is automatically built, pushed to Amazon ECR, and deployed to Amazon ECS Fargate on every code push.

---

## ⭐ Key Highlights

* Designed a **production-ready CI/CD pipeline** on AWS
* Automated **build, test, and deployment** using GitHub Actions
* Implemented **containerized deployment** using Docker and Amazon ECS Fargate
* Integrated **Application Load Balancer (ALB)** for high availability
* Achieved **zero-downtime deployment**
* Optimized **cost using on-demand deployment strategy**

---

## 🧠 Core Value Proposition

> Built a fully automated CI/CD pipeline that deploys a containerized application to AWS ECS Fargate with zero manual intervention.

---

## 🏗️ Architecture Overview

This project demonstrates a full CI/CD pipeline using:

GitHub → GitHub Actions → Docker → Amazon ECR → Amazon ECS (Fargate) → ALB → Users

---

## 🏗️ Production Architecture

![Architecture](./architecture.png)

---
## 📸 Application Preview

Below is the live UI of the deployed application served via AWS ALB:

![App Screenshot](./app-preview.png)

---

## 🧰 Tech Stack

* **Backend:** Node.js
* **Containerization:** Docker
* **CI/CD:** GitHub Actions
* **Cloud Provider:** AWS

  * Amazon ECR (Container Registry)
  * Amazon ECS (Fargate)
  * Application Load Balancer (ALB)
* **Infrastructure:** AWS Console

---

## ⚙️ CI/CD Pipeline

The deployment pipeline is fully automated:

1. Code is pushed to the `main` branch
2. GitHub Actions workflow is triggered
3. Docker image is built
4. Image is tagged and pushed to Amazon ECR
5. ECS service is updated
6. New container is deployed automatically

---

## 🔄 CI/CD Trigger

The pipeline is triggered automatically by:

* ✅ Push to `main` branch
* ✅ Manual trigger via GitHub Actions (optional)
* ✅ Empty commit (for testing pipeline)

Example:

```
git commit --allow-empty -m "trigger pipeline"
git push
```

---

## 🔐 GitHub Secrets

The following secrets are configured for secure deployment:

* `AWS_ACCESS_KEY_ID`
* `AWS_SECRET_ACCESS_KEY`
* `AWS_ACCOUNT_ID`
* `AWS_REGION`
* `ECR_REPOSITORY`
* `ECS_CLUSTER`
* `ECS_SERVICE`

---

## 🐳 Docker

Build image locally:

```
docker build -t food-menu-service .
```

Run container:

```
docker run -p 3000:3000 food-menu-service
```

---

## ▶️ Run Locally

```
npm install
npm start
```

App will run on:

```
http://localhost:3000
```

---

## ☁️ Deployment

Deployment is handled automatically via GitHub Actions.

Every push to `main` will:

* Build a new Docker image
* Push to ECR
* Trigger ECS deployment

---

## 🌐 Live Application

The application is exposed through an AWS Application Load Balancer (ALB).

Example:

```
http://<your-alb-dns>
```

---
## 🧠 Design Decisions

### Why ECS Fargate instead of EC2
ECS Fargate was chosen to avoid managing EC2 instances, operating system updates, and cluster capacity planning.  
Compared to EC2 Auto Scaling, Fargate reduces operational overhead and is better suited for a small-to-medium stateless application where infrastructure simplicity is more important than low-level instance control.

### Why Amazon ECR for image storage
Amazon ECR was used as the container registry because it integrates natively with ECS and simplifies authentication and image management.  
Compared to using Docker Hub or another external registry, ECR reduces friction in the deployment workflow and keeps container images within the AWS ecosystem.

### Why GitHub Actions for CI/CD
GitHub Actions was used to automate the build and deployment pipeline directly from the GitHub repository.  
Compared to Jenkins or self-hosted CI/CD tools, GitHub Actions requires less setup and maintenance, which makes it a practical choice for lightweight, repository-driven automation.

### Why Application Load Balancer (ALB)
An Application Load Balancer was used to provide a single public entry point and route traffic to healthy ECS tasks.  
Compared to direct task access, ALB improves reliability by supporting health checks and traffic distribution, and it also makes the architecture easier to scale later.

### Why manual AWS Console setup for this project
For this version of the project, AWS resources were provisioned manually through the AWS Console to focus on understanding the deployment flow and service integration first.  
In a production environment, this infrastructure would be managed using Infrastructure as Code tools such as Terraform to improve repeatability, consistency, and team collaboration.

### Why on-demand deployment strategy
AWS resources such as ECS services and ALB were cleaned up after testing to avoid unnecessary ongoing cloud costs.  
This approach is cost-efficient for portfolio projects and demos, while still allowing the system to be redeployed quickly through the existing CI/CD pipeline.

---
## 📈 Key Features

* Fully automated CI/CD pipeline
* Containerized application using Docker
* Serverless container deployment with ECS Fargate
* Scalable and production-ready architecture
* Secure credential management using GitHub Secrets

---

## 🧠 What I Learned

* Building end-to-end CI/CD pipelines
* Integrating GitHub Actions with AWS
* Managing containerized deployments on ECS
* Working with AWS networking and load balancing
* Debugging deployment pipelines and cloud services

---

## 📬 Contact

If you have any questions or feedback, feel free to reach out!

---

⭐ If you find this project helpful, consider giving it a star!
