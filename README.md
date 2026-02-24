# 🚀 Full CI/CD Pipeline with Jenkins, Docker & Docker Compose

This project demonstrates a complete CI/CD pipeline using:

- ✅ GitHub Webhooks
- ✅ Jenkins Pipeline
- ✅ Docker & DockerHub
- ✅ Docker Compose Deployment
- ✅ AWS EC2 Hosting
- ✅ MongoDB + Backend + Frontend Application

---

# 🏗️ Architecture Overview

GitHub → Webhook → Jenkins → Build Docker Images → Push to DockerHub → Deploy using Docker Compose → Application Live on EC2

---

# 📂 Project Structure

---

# ⚙️ Step 1: GitHub Webhook Configuration

Webhook triggers Jenkins pipeline automatically on code push.

📸 Screenshot:

![GitHub Webhook](screenshots/094011.png)

---

# ⚙️ Step 2: Jenkins Shared Library Configuration

Jenkins configured with shared library from GitHub.

📸 Screenshot:

![Jenkins Shared Library](screenshots/094226.png)

---

# ⚙️ Step 3: Jenkins Pipeline Parameters

Pipeline configured with parameters:

- FRONTEND_DOCKER_TAG
- BACKEND_DOCKER_TAG

📸 Screenshot:

![Pipeline Parameters](screenshots/100634.png)

---

# ⚙️ Step 4: Pipeline Stage View (Failed Build Example)

Initial pipeline failures during Docker login & push.

📸 Screenshot:

![Failed Pipeline](screenshots/103249.png)

📸 Screenshot:

![Failed Stage View](screenshots/103308.png)

---

# ⚙️ Step 5: Docker Compose Configuration

`docker-compose.yml` defines:

- Backend (Port 8080)
- Frontend (Port 80)
- MongoDB (Port 27017)

📸 Screenshot:

![Docker Compose File](screenshots/103354.png)

📸 Screenshot:

![Docker Compose GitHub View](screenshots/103423.png)

---

# ⚙️ Step 6: Successful Pipeline Execution

Pipeline stages:

- Checkout SCM
- Validate Parameters
- Git Checkout
- Docker Build
- Docker Login
- Docker Push
- Deploy via Docker Compose

📸 Screenshot:

![Successful Pipeline](screenshots/103447.png)

📸 Screenshot:

![Final Successful Build](screenshots/103543.png)

---

# 🐳 Docker Images Built

Images created:

- `akash1729/cron-backend`
- `akash1729/cron-frontend`

📸 Screenshot:

![Docker Images](screenshots/104133.png)

---

# 🚀 Docker Containers Running

Running containers:

- crud-backend (8080)
- crud-frontend (80)
- mongodb (27017)

📸 Screenshot:

![Docker Containers](screenshots/104150.png)

---

# 🌐 Application Deployment

Application deployed and accessible via:



📸 Screenshot:

![Application UI](screenshots/104238.png)

📸 Screenshot:

![Add Tutorial Page](screenshots/104244.png)

📸 Screenshot:

![Submission Success](screenshots/104302.png)

📸 Screenshot:

![Tutorial List View](screenshots/104321.png)

---

# 🔐 DockerHub Login Stage Logs

Docker login configured using Jenkins Secret Text credentials.

📸 Screenshot:

![Docker Login Logs](screenshots/100634.png)

---

# 🔥 CI/CD Flow Summary

1. Developer pushes code to GitHub
2. GitHub Webhook triggers Jenkins
3. Jenkins builds Docker images
4. Images pushed to DockerHub
5. Docker Compose deploys containers
6. Application automatically updated on EC2

---

# 🧠 Key Learning Outcomes

- Automated CI/CD pipeline setup
- Secure DockerHub credential management
- Jenkins parameterized pipeline
- Docker Compose multi-container deployment
- Webhook-based auto deployment
- Real-world DevOps workflow on AWS EC2

---
