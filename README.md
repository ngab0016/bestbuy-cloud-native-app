# Best Buy Cloud-Native Application 🚀

> A scalable, microservices-based e-commerce platform built with modern cloud-native technologies

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)]()
[![Kubernetes](https://img.shields.io/badge/Kubernetes-AKS-326CE5?logo=kubernetes)]()
[![Docker](https://img.shields.io/badge/Docker-Hub-2496ED?logo=docker)]()
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?logo=github-actions)]()

---

## 📋 Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Repository Links](#repository-links)
- [Docker Images](#docker-images)
- [Deployment Guide](#deployment-guide)
- [CI/CD Pipeline](#cicd-pipeline)
- [Demo Video](#demo-video)
- [Contributors](#contributors)

---

## 🎯 Overview

This project demonstrates a production-ready, cloud-native e-commerce application built for Best Buy. The application follows microservices architecture principles and implements DevOps best practices including containerization, orchestration, and automated CI/CD pipelines.

**Key Highlights:**
- 🏗️ Microservices architecture with 6 independent services
- ☸️ Deployed on Azure Kubernetes Service (AKS)
- 🔄 Automated CI/CD with GitHub Actions
- 📊 Scalable and resilient infrastructure
- 🔐 Secure configuration management with Secrets and ConfigMaps

---

## 🏛️ Architecture

![alt text](<Full-Stack Architecture.drawio.png>)

### System Components

| Component | Purpose | Technology |
|-----------|---------|------------|
| **Store-Front** | Customer-facing web application | React/Node.js |
| **Store-Admin** | Employee management dashboard | React/Node.js |
| **Order-Service** | Order processing and management | Node.js/Express |
| **Product-Service** | Product catalog management | Node.js/Express |
| **Makeline-Service** | Background order processing worker | Node.js |
| **AI-Service** | AI-powered recommendations | Python/Flask |
| **MongoDB** | Persistent data storage | MongoDB (StatefulSet) |
| **RabbitMQ** | Message queue for async communication | RabbitMQ (StatefulSet) |

### Architecture Flow

1. **Customer Journey**: Users interact with Store-Front → requests routed to Product/Order services
2. **Order Processing**: Orders published to RabbitMQ → consumed by Makeline-Service
3. **Admin Operations**: Employees use Store-Admin → manage products and orders
4. **AI Integration**: AI-Service provides intelligent product recommendations
5. **Data Persistence**: MongoDB stores all application data using StatefulSets

---

## ✨ Features

### Customer Features (Store-Front)
- 🛍️ Browse product catalog
- 🔍 Search and filter products
- 🛒 Shopping cart management
- 📦 Order placement and tracking
- 🤖 AI-powered product recommendations

### Admin Features (Store-Admin)
- 📊 Dashboard with analytics
- 📦 Product management (CRUD operations)
- 📋 Order management and fulfillment
- 👥 Customer data insights

### Technical Features
- ⚡ High availability with replica sets
- 📈 Horizontal pod autoscaling
- 🔄 Rolling updates with zero downtime
- 🔒 Secure secrets management
- 📝 Centralized logging and monitoring

---

## 🛠️ Technology Stack

### Frontend
- React.js
- HTML5/CSS3/JavaScript
- Bootstrap/Material-UI

### Backend
- Node.js / Express.js
- Python / Flask (AI Service)
- RESTful APIs

### Infrastructure
- **Container Runtime**: Docker
- **Orchestration**: Kubernetes (AKS)
- **Cloud Provider**: Microsoft Azure
- **CI/CD**: GitHub Actions
- **Container Registry**: Docker Hub

### Data Layer
- **Database**: MongoDB (StatefulSet)
- **Message Queue**: RabbitMQ
- **Configuration**: ConfigMaps & Secrets

---

## 📦 Repository Links

| Service | GitHub Repository | Status |
|---------|------------------|--------|
| Store-Front | https://github.com/ngab0016/store-front-L8 | ✅ Active |
| Store-Admin | https://github.com/ngab0016/store-admin-L8 | ✅ Active |
| Order-Service | https://github.com/ngab0016/order-service-L8) | ✅ Active |
| Product-Service | https://github.com/ngab0016/product-service-L8 | ✅ Active |
| Makeline-Service | https://github.com/ngab0016/makeline-service-L8 | ✅ Active |
| AI-Service | [github.com/YOUR_USERNAME/ai-service-l8](https://github.com/YOUR_USERNAME/ai-service-l8) | ✅ Active |

---

## 🐳 Docker Images

| Service | Docker Hub Image |
|---------|-----------------|
| Store-Front | [darkxnight/store-front-l8](https://hub.docker.com/r/darkxnight/store-front-l8) |
| Store-Admin | [darkxnight/store-admin-l8](https://hub.docker.com/r/darkxnight/store-admin-l8) |
| Order-Service | [darkxnight/order-service-l8](https://hub.docker.com/r/darkxnight/order-service-l8) |
| Product-Service | [darkxnight/product-service-l8](https://hub.docker.com/r/darkxnight/product-service-l8) |
| Makeline-Service | [darkxnight/makeline-service-l8](https://hub.docker.com/r/darkxnight/makeline-service-l8) |
| AI-Service | [darkxnight/ai-service-l8](https://hub.docker.com/r/darkxnight/ai-service-l8) |

---

## 🚀 Deployment Guide

### Prerequisites
- Azure account with active subscription
- Azure CLI installed
- kubectl installed
- Docker Hub account

### Quick Deployment

```bash
# 1. Create AKS cluster
az aks create \
  --resource-group bestbuy-rg \
  --name bestbuy-aks \
  --node-count 2 \
  --node-vm-size Standard_B2ms \
  --enable-addons monitoring \
  --generate-ssh-keys

# 2. Get credentials
az aks get-credentials --resource-group bestbuy-rg --name bestbuy-aks

# 3. Deploy all services
kubectl apply -f "Deployment Files/"

# 4. Verify deployment
kubectl get all
```

### Detailed Instructions
See [Deployment Guide](./docs/deployment-guide.md) for step-by-step instructions.

---

## 🔄 CI/CD Pipeline

Each microservice has an automated CI/CD pipeline that:

1. **Build**: Compiles code and creates Docker images
2. **Test**: Runs unit and integration tests
3. **Push**: Uploads images to Docker Hub
4. **Deploy**: Updates Kubernetes deployments automatically

### Pipeline Workflow

```
Code Push → GitHub Actions → Build Image → Run Tests → Push to Docker Hub → Deploy to AKS
```

### Viewing Pipeline Status
- Go to any repository → Actions tab
- View real-time build logs and deployment status

---

## 🎥 Demo Video

**Watch the full demonstration**: https://youtu.be/FuPlzp8bbx0

---

## 👨‍💻 Contributors

- **Your Name** - Full-Stack Cloud-Native Developer
- **Student ID**: 041196196
- **Course**: CST8915 - Full-stack Cloud-native Development
- **Institution**: Algonquin College

---

