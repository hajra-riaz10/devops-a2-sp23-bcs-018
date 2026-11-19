# DevOps Assignment 2: Build, Containerize and Automate

**Course:** DevOps for Cloud Computing (Lab)  
**Student Name:** Hajira Riaz  
**Registration Number:** SP23-BCS-018  
**Department:** Computer Science  
**Institution:** COMSATS University Islamabad, Attock Campus  

---

## Project Overview

This repository contains a containerized personal portfolio web application built with plain HTML and CSS. The project demonstrates modern DevOps practices, including:
- Version control and branching strategies with **Git and GitHub**.
- Lightweight containerization using **Docker** and **Nginx**.
- Automated continuous integration and deployment with **GitHub Actions**.
- Webhook event notifications via **webhook.site**.

---

## Local Development and Docker Run

### Prerequisites
- Docker Desktop installed and running.

### 1. Build Docker Image
```bash
docker build -t hajra1278/devops-a2:manual .
```

### 2. Run Container
```bash
docker run -d -p 8080:80 --name page hajra1278/devops-a2:manual
```

### 3. Access Application
Open your web browser and navigate to:
```
http://localhost:8080
```

---

## CI/CD Pipeline (.github/workflows/ci.yml)
- **Triggers:** Push to `main` and Pull Requests.
- **Automated Validation:**
  - Verifies presence of `index.html` and `style.css`.
  - Ensures `<title>` tag exists.
  - Validates roll number `SP23-BCS-018` is present.
- **Docker Hub Deployment:**
  - On pull requests: Builds image without pushing.
  - On `main` branch pushes: Authenticates with Docker Hub secrets and pushes `hajra1278/devops-a2:latest`.
