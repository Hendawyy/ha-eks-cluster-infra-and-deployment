# 🚀 3-Tier Application Deployment on AWS EKS

This repository contains the Kubernetes manifests and configuration files used to deploy a highly available (HA) 3-tier web application on an Amazon EKS (Elastic Kubernetes Service) cluster.

## ⚙️ Prerequisites

- `AWS CLI`
- `kubectl`
- `eksctl`
- IAM permissions to create EKS resources

## 🚀 Application Overview

This is a simple 3-tier application consisting of:

- **Frontend**: Static HTML/JS app served over NGINX
- **Backend**: Node.js API that maintains a counter
- **Ingress**: NGINX Ingress Controller with an Ingress resource routing `/` to frontend and `/api/` to backend

## 📦 Deployment Highlights

- **Highly Available EKS Cluster** deployed across multiple AZs
- **Managed & Self-Managed Node Groups** used for control and flexibility
- **Ingress Controller** exposed via LoadBalancer with routing rules
- **TopologySpreadConstraints** used to evenly distribute pods across AZs
- **ClusterIP Services** for internal communication; exposed via Ingress

## 🌐 Access

Once deployed, the application is accessible via the Ingress Controller's external DNS name:

```bash
http://<external-dns-of-nginx-ingress>
```
