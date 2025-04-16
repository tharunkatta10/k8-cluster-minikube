# Kubernetes Cluster Setup and Node.js App Deployment

## Overview
This repository demonstrates the process of setting up a Kubernetes cluster using Minikube and deploying a Node.js application (`wisecow-node-app`). The app is containerized with Docker, deployed on Kubernetes, and exposed via a service. The project covers the setup of Kubernetes, Node.js app deployment, and related troubleshooting.

## Folder Structure
```
wisecow-node-app/
│
├── Dockerfile               # Dockerfile for containerizing the Node.js app
├── package.json             # Node.js app dependencies
├── k8s/                     # Kubernetes configuration files
│   ├── deployment.yaml      # Deployment configuration for the app
│   └── service.yaml         # Service configuration to expose the app
├── screenshots/             # Folder for project-related screenshots
└── README.md                # Documentation for the repository
```

## Prerequisites
- Minikube installed on your machine
- Docker installed and running
- Kubernetes CLI (`kubectl`) configured

## Setup and Installation

### Minikube Cluster Setup
1. **Start Minikube**:
   ```bash
   minikube start
   ```

2. **Verify Minikube Cluster**:
   Ensure the Kubernetes cluster is running properly.
   ```bash
   kubectl cluster-info
   ```

### Docker Setup for Node.js Application
1. **Build Docker Image**:
   Navigate to the root directory of your project, where the `Dockerfile` is located, and build the Docker image:
   ```bash
   docker build -t wisecow-node-app .
   ```

2. **Push Docker Image to DockerHub** (Optional, if pushing to a remote repository):
   ```bash
   docker push your-dockerhub-username/wisecow-node-app
   ```

### Kubernetes Deployment
1. **Deploy the Application**:
   Apply the Kubernetes manifests for deployment and service:
   ```bash
   kubectl apply -f k8s/deployment.yaml
   kubectl apply -f k8s/service.yaml
   ```

2. **Expose the App**:
   If the service is a `NodePort`, you can expose it using the following:
   ```bash
   kubectl port-forward service/wisecow-service 3000:80
   ```

### Access the Application
Open a browser and navigate to `http://localhost:3000` to access the deployed app.

## Troubleshooting
- **Port Forwarding Issue**: If you face issues with port-forwarding, ensure that the service and pods are running correctly:
  ```bash
  kubectl get pods
  kubectl get services
  ```

## Conclusion
This repository provides a simple walkthrough of deploying a Node.js application to a Minikube-managed Kubernetes cluster. Despite the challenges with port-forwarding, the core deployment steps and service exposure methods are well illustrated. The project is designed to be a reference for Docker, Kubernetes, and Node.js app deployment.

## Screenshots
Refer to the `screenshots/` directory for visual insights into the process and app.

## Author
**Name**: Tharun Katta  
**Email**: tharunkatta10@gmail.com  
**Phone**: +91 9441684297  
**GitHub**: [tharunkatta10](https://github.com/tharunkatta10)  
**Location**: Bangalore, India


