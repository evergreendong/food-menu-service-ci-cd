# 🚀 Food Menu Service - CI/CD on AWS

## 📌 Overview

This project demonstrates a **production-ready CI/CD pipeline** using GitHub Actions and AWS services.

A Dockerized Node.js application is automatically built, pushed to Amazon ECR, and deployed to Amazon ECS Fargate on every code push.

---

## 🏗️ Architecture Overview


This project demonstrates a production-ready CI/CD pipeline using GitHub Actions, Docker, Amazon ECR, and ECS Fargate behind an Application Load Balancer.

## 🏗️ Production Architecture

![Architecture](./architecture.png)
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
