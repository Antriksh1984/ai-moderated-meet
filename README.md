# 🚀 AI-Moderated WebRTC Video Platform (Azure + Kubernetes)

A cloud-native, production-grade real-time video conferencing platform with **AI-powered content moderation**, built using WebRTC, Kubernetes (AKS), and Azure AI services.

---

## 🌟 Features

* 🎥 Real-time video conferencing (WebRTC)
* 🔌 Socket.IO signaling server
* ☁️ Cloud-native deployment on Azure Kubernetes Service (AKS)
* 🔁 CI/CD pipeline using GitHub Actions
* 📦 Azure Container Registry (ACR) integration
* 🤖 AI-powered content moderation (Azure AI Content Safety)
* 📊 Observability-ready (Prometheus + Grafana)
* ⚡ Scalable microservices architecture

---

## 🏗️ Tech Stack

| Layer            | Technology                              |
| ---------------- | --------------------------------------- |
| Frontend         | React                                   |
| Backend          | Node.js + Socket.IO                     |
| Realtime         | WebRTC                                  |
| Containerization | Docker                                  |
| Orchestration    | Kubernetes (AKS)                        |
| CI/CD            | GitHub Actions                          |
| Cloud            | Microsoft Azure                         |
| Registry         | Azure Container Registry                |
| AI Moderation    | Azure AI Content Safety / Video Indexer |

---

## 📦 Project Structure

```text
.
├── client/                     # React frontend
├── server/                     # Node.js + Socket.IO backend
├── k8s/                        # Kubernetes manifests
├── .github/workflows/ci.yml    # CI/CD pipeline
└── docker-compose.yml          # Local development
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

On push to `main`:

1. Build Docker images (client + server)
2. Push images to Azure Container Registry (ACR)
3. Deploy images to Azure Kubernetes Service (AKS)

---

## ☁️ Deployment (AKS)

```bash
kubectl apply -f k8s/
```

Verify:

```bash
kubectl get pods
kubectl get svc
```

---

## 🌐 Access Application

```bash
kubectl get svc meet-client-service
```

Open the external IP in your browser.

---

# 🤖 AI Content Moderation (Core Feature)

This platform integrates **Azure AI Content Safety** to automatically detect:

* 🚫 Hate speech
* 🔞 Sexual content
* ⚠ Violence
* 🧠 Harmful or abusive behavior

---

## 🧠 How AI Moderation Works

### 🔄 Flow

```text
User Video Stream
        ↓
Backend (Node.js)
        ↓
Frame Extraction (periodic snapshots)
        ↓
Azure AI Content Safety API
        ↓
Moderation Decision Engine
        ↓
✔ Allow   ⚠ Flag   ❌ Block User
```

---

## ⚙️ Implementation Strategy

### Option 1 — Real-time moderation (advanced)

* Extract frames every few seconds
* Send to Azure AI API
* Take action instantly (mute / disconnect)

### Option 2 — Async moderation (recommended initial approach)

* Record session
* Upload to Azure Blob Storage
* Run AI analysis post-call

---

## 🧠 Sample Backend Integration (Pseudo Code)

```javascript
const response = await axios.post(AZURE_AI_ENDPOINT, {
  image: frameData
});

if (response.data.riskLevel > threshold) {
  disconnectUser(socket.id);
}
```

---

## ⚠️ Constraints

* WebRTC camera requires **HTTPS (secure context)**
* Socket.IO scaling requires **sticky sessions or single replica**
* AI moderation latency depends on API response time

---

## 🔐 Future Improvements

* 🌐 Ingress + HTTPS (Let’s Encrypt)
* 📊 Prometheus + Grafana monitoring
* 📈 Horizontal Pod Autoscaling (HPA)
* 🧠 Real-time speech moderation
* 📦 Azure Event-driven moderation pipeline
* 🧾 Audit logs & moderation dashboard

---

## 🧠 Architecture Overview

* Microservices deployed on AKS
* CI/CD automated via GitHub Actions
* Images stored in Azure Container Registry
* Real-time communication via WebRTC + Socket.IO
* AI moderation integrated via Azure AI APIs

---

## 👨‍💻 Author

Built as a full-stack cloud-native system demonstrating:

* Kubernetes (AKS)
* Azure Cloud
* DevOps pipelines
* Real-time systems (WebRTC)
* AI integration in production

---

🔥 This project represents an end-to-end scalable AI-powered system.
