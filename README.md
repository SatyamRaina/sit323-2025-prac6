# SIT323/SIT737 – Cloud Native Application Development

## Task 6.1P: Deploying a Containerized Node.js Application to Kubernetes

---

## 🚀 Overview

This project demonstrates the complete workflow of containerizing a Node.js calculator microservice and deploying it to a Kubernetes cluster. The application exposes multiple arithmetic operations via HTTP endpoints and is accessible externally through a NodePort service.

The Kubernetes cluster was set up locally using Docker Desktop with Kubernetes enabled. Deployment and service configuration were done using Kubernetes YAML manifests.

---

## 🛠 Tools and Technologies

- **Node.js** — Backend application
- **Express.js** — Web framework
- **Docker** — Containerization
- **Docker Hub** — Image registry
- **Kubernetes** — Container orchestration
- **kubectl CLI** — Kubernetes management tool
- **Kubernetes Dashboard** — GUI for cluster visualization
- **Visual Studio Code** — Code editor

---

## 📋 Project Structure
```
week6task/
├── deployment.yaml        # Kubernetes Deployment configuration
├── Dockerfile              # Docker build file
├── package.json            # Node.js project metadata
├── package-lock.json       # Node.js dependency lock file
├── service.yaml            # Kubernetes Service configuration
├── test.js                 # Calculator microservice source code
├── .gitignore              # Specifies files/folders to be ignored by Git
└── README.md               # Project documentation (this file)
```

## 🧩 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/SatyamRaina/sit323-2025-prac6.git
cd sit323-2025-prac6/week6task
```

## Build and Push Docker Image
```baash
docker build -t satyamraina/week6task-calculator:latest .
docker push satyamraina/week6task-calculator:latest
```

## Deploy to Kubernetes
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

## Verify Deployment
```bash
kubectl get pods
kubectl get svc
```

✅ You should see the service calculator-service exposed on NodePort 30081.

🌐 Access the Calculator Microservice

Open your browser and test the following endpoints:
```bash
Endpoint Example	Operation
http://localhost:30081/add?n1=5&n2=3	Addition
http://localhost:30081/subtract?n1=10&n2=4	Subtraction
http://localhost:30081/multiply?n1=7&n2=6	Multiplication
http://localhost:30081/divide?n1=20&n2=4	Division
http://localhost:30081/power?n1=2&n2=3	Power
http://localhost:30081/mod?n1=10&n2=3	Modulus
http://localhost:30081/sqrt?n1=16	Square Root
http://localhost:30081/calculate?n1=5&n2=3&operation=add	Dynamic operation (generic route)
```
📚 Learning Outcomes

1. Building and managing containerized applications.
2. Deploying containerized applications to Kubernetes.
3. Exposing applications using Kubernetes Services.
4. Managing deployments through YAML configuration files.
5. Using Kubernetes Dashboard for visual monitoring.

Satyam Raina
Bachelor of Software Engineering (Honours) - Cloud Computing Major
Deakin University, Australia
