# 🚀 AI Moderated WebRTC Video Platform (Azure + Kubernetes)

A production-grade real-time video conferencing platform built with **WebRTC, Socket.IO, Docker, Kubernetes (AKS), and Azure DevOps tools**, enhanced with AI-based content moderation.

---

## 🌟 Features

* 🎥 Real-time video communication (WebRTC)
* 🔌 Socket.IO signaling server
* ⚡ Scalable microservices architecture (Docker + Kubernetes)
* ☁️ Deployed on Azure Kubernetes Service (AKS)
* 🔁 CI/CD pipeline using GitHub Actions
* 📦 Container registry using Azure Container Registry (ACR)
* 📊 Observability ready (Prometheus + Grafana)
* 🧠 AI moderation pipeline (Azure-based)

---

## 🏗️ Tech Stack

| Layer            | Tech                     |
| ---------------- | ------------------------ |
| Frontend         | React                    |
| Backend          | Node.js + Socket.IO      |
| Realtime         | WebRTC                   |
| Containerization | Docker                   |
| Orchestration    | Kubernetes (AKS)         |
| CI/CD            | GitHub Actions           |
| Cloud            | Azure                    |
| Registry         | Azure Container Registry |
| Monitoring       | Prometheus + Grafana     |

---

## 📦 Project Structure

```
.
├── client/          # React frontend
├── server/          # Socket.IO backend
├── k8s/             # Kubernetes manifests
├── .github/workflows/ci.yml   # CI/CD pipeline
└── docker-compose.yml         # Local dev setup
```

---

## ⚙️ Local Development

```bash
docker-compose up --build
```

Access:

* Frontend → http://localhost:3000
* Backend → http://localhost:3001

---

## 🚀 CI/CD Pipeline

On every push to `main`:

1. Build Docker images
2. Push to Azure Container Registry (ACR)
3. Ready for Kubernetes deployment

---

## ☁️ Deployment (AKS)

```bash
kubectl apply -f k8s/
```

Check:

```bash
kubectl get pods
kubectl get svc
```

---

## 🌐 Access Application

```bash
kubectl get svc meet-client-service
```

Open EXTERNAL-IP in browser.

---

## ⚠️ Known Constraints

* Camera access requires **HTTPS (WebRTC security restriction)**
* Socket.IO scaling requires sticky sessions or single replica

---

## 🔐 Future Improvements

* Ingress + HTTPS (Let's Encrypt)
* Horizontal scaling with sticky sessions
* AI moderation integration pipeline
* Autoscaling (HPA)
* Logging (ELK / Azure Monitor)

---

## 🧠 Architecture Highlights

* Microservices deployed on AKS
* Container images stored in ACR
* CI/CD fully automated via GitHub Actions
* Real-time communication handled via WebRTC + Socket.IO

---

## 👨‍💻 Author

Built as a cloud-native, production-grade system for learning and showcasing:

* Kubernetes
* Azure Cloud
* DevOps pipelines
* Real-time systems

---

🔥 This project demonstrates end-to-end cloud-native system design.
