# 🚀 Reactfolio End-to-End Deployment with Docker, Kubernetes & Jenkins CI/CD

```{=html}
<p align="center">
```
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestrated-326CE5?logo=kubernetes)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red?logo=jenkins)
![GitHub](https://img.shields.io/badge/GitHub-Webhooks-black?logo=github)
![React](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react)

```{=html}
</p>
```
## 📖 Overview

This repository demonstrates a complete **end-to-end DevOps
implementation** for deploying a React application using modern DevOps
practices.

Unlike a simple Docker deployment, this project covers the complete
deployment lifecycle:

-   Source Control with Git & GitHub
-   Docker Image Creation
-   Container Registry (Docker Hub)
-   Kubernetes Deployment
-   NGINX Ingress Routing
-   Jenkins Continuous Integration & Continuous Deployment
-   GitHub Webhooks
-   Automatic Deployment after every Git Push

The goal of this repository is educational. It demonstrates how
developers and DevOps engineers automate deployments from source code to
a running Kubernetes application.

------------------------------------------------------------------------

# 🙏 Acknowledgement

The frontend used in this project is based on the open-source
**Reactfolio** project by **@truethari**.

**Original Repository**

https://github.com/truethari/reactfolio

All credit for the React portfolio application belongs to the original
author.

This repository focuses on the **DevOps implementation**, including
Dockerization, Kubernetes manifests, Jenkins CI/CD pipeline, GitHub
Webhooks, deployment automation, and infrastructure documentation.

------------------------------------------------------------------------

# 🏗 Architecture

``` text
Developer
    │
    │ git push
    ▼
GitHub Repository
    │
    ▼
GitHub Webhook
    │
    ▼
ngrok Tunnel
    │
    ▼
Jenkins Pipeline
    │
    ├──────── Checkout Source
    ├──────── Docker Build
    ├──────── Docker Push
    └──────── Kubernetes Deployment
                     │
                     ▼
            Minikube Kubernetes
                     │
        Deployment → Service → Ingress
                     │
                     ▼
             Reactfolio Application
```

------------------------------------------------------------------------

# ✨ Features

-   End-to-End CI/CD
-   Automatic Deployment after Git Push
-   Dockerized React Application
-   Kubernetes Deployment with 3 Replicas
-   ClusterIP Service
-   NGINX Ingress Controller
-   Jenkins Pipeline (UI Based)
-   Docker Hub Integration
-   GitHub Webhooks
-   Local domain mapping with /etc/hosts/
-   Use of ngrok for exposing jenkins to Internet
-   Local Production-like Environment using Minikube

------------------------------------------------------------------------

# 🛠 Tech Stack

  Category           Technology
  ------------------ --------------------------
  Frontend           React
  Containerization   Docker
  Registry           Docker Hub
  Orchestration      Kubernetes (Minikube)
  Ingress            NGINX Ingress Controller
  CI/CD              Jenkins
  SCM                Git & GitHub
  Webhook Tunnel     ngrok
  OS                 Ubuntu WSL

------------------------------------------------------------------------

# 📂 Project Structure

``` text
reactfolio/
│
├── src/
├── public/
├── Dockerfile
├── package.json
├── package-lock.json
├── README.md
│
└── k8s/
    ├── reactfolio-deployment.yaml
    ├── reactfolio-service.yaml
    └── ingress.yaml
```

------------------------------------------------------------------------

# ⚙ CI/CD Workflow

``` text
Code Change
      │
git add .
git commit
git push
      │
      ▼
GitHub
      │
Webhook
      ▼
Jenkins
      │
Checkout Code
      │
Docker Build
      │
Docker Push
      │
kubectl rollout restart
      ▼
Updated Application
```

------------------------------------------------------------------------

# 🔄 Jenkins Pipeline Stages

## 1. Checkout Source Code

Downloads the latest code from GitHub into the Jenkins workspace.

## 2. Docker Build

Builds a Docker image using the Dockerfile in the repository.

## 3. Docker Push

Pushes the image to Docker Hub.

## 4. Kubernetes Deployment

Triggers a rolling restart so Kubernetes deploys the updated image.

------------------------------------------------------------------------

# ☸ Kubernetes Components

## Deployment

-   Maintains desired replicas
-   Performs rolling updates
-   Self-heals failed pods

## Service

-   ClusterIP for internal communication

## Ingress

-   Routes HTTP traffic to the ClusterIP service
-   Makes the application accessible using a domain inside Minikube

------------------------------------------------------------------------

# 📸 Screenshots

Create a folder named:

``` text
screenshots/
```

Suggested screenshots:

-   GitHub Repository
-   Jenkins Dashboard
-   Successful Pipeline
-   Docker Hub Repository
-   Running Pods
-   Services
-   Ingress
-   Application Home Page

Example:

``` markdown
## Jenkins Pipeline

![Pipeline](screenshots/pipeline.png)
```

------------------------------------------------------------------------

# 🚀 Local Setup

1.  Clone repository
2.  Install Docker
3.  Start Minikube
4.  Enable Ingress
5.  Apply Kubernetes manifests
6.  Install Jenkins
7.  Configure Docker permissions
8.  Configure kubeconfig for Jenkins
9.  Configure Docker Hub login
10. Configure GitHub Webhook
11. Push code and enjoy automated deployment

------------------------------------------------------------------------

# 🐞 Troubleshooting

During this project the following real-world issues were solved:

-   Docker daemon permission denied
-   Jenkins Docker socket permissions
-   GitHub HTTPS authentication
-   Docker Hub authorization
-   Kubernetes kubeconfig missing for Jenkins
-   Minikube certificate permissions
-   Jenkins CSRF (Crumb) protection
-   GitHub Webhook configuration
-   ngrok public tunnel
-   Ingress routing
-   React SPA routing

------------------------------------------------------------------------

# 📚 Learning Outcomes

This project provided practical experience with:

-   Git
-   Docker
-   Docker Hub
-   Kubernetes
-   Pods vs Deployments
-   Services
-   Ingress
-   Jenkins
-   CI/CD
-   GitHub Webhooks
-   Linux permissions
-   Production deployment concepts
-   Troubleshooting real DevOps issues

------------------------------------------------------------------------

# 👨‍💻 Author

**Sai Ghaware**

This project was created for learning modern DevOps practices and
demonstrating practical deployment skills for portfolio purposes.

------------------------------------------------------------------------

# 📄 License & Attribution

This repository includes a frontend derived from the original Reactfolio
project.

Frontend credit remains with the original author:

https://github.com/truethari/reactfolio

The DevOps workflow, containerization, Kubernetes configuration, Jenkins
pipeline, deployment automation, troubleshooting documentation, and
CI/CD implementation contained in this repository were independently
developed for educational and portfolio purposes.

------------------------------------------------------------------------

⭐ If you found this repository useful, consider giving it a star!
