# Internal Developer Platform Demo Repo

## 🚀 Overview
This repository demonstrates how to build a simple Internal Developer Platform (IDP) using:
- **Kubernetes** for orchestration
- **GitOps with ArgoCD** for deployment automation
- **Helm** for packaging
- **ChatGPT** for AI-assisted developer workflows

Designed to run on **Minikube** (for local demo) or **EKS** (for production-like environments).

---

## 🧱 Repository Structure

```
internal-dev-platform-demo/
├── README.md
├── docs/
│   ├── architecture.md
│   ├── golden-paths.md
│   └── ai-prompts.md
├── platform/
│   ├── helm-charts/
│   │   └── sample-app/
│   ├── argocd/
│   │   └── apps/
│   │       └── sample-app.yaml
│   └── manifests/
├── templates/
│   └── nodejs-service/
│       ├── k8s/
│       │   ├── deployment.yaml
│       │   └── service.yaml
│       ├── Dockerfile
│       └── app/
│           └── index.js
└── tools/
    └── devctl.sh
```

---

## ⚙️ Prerequisites
- Minikube or EKS Cluster
- kubectl
- Helm
- ArgoCD CLI (optional but useful)
- GitHub account to fork this repo

---

## 🔧 Setup Instructions

### 1. Start Minikube (or use EKS)
```bash
minikube start
```

### 2. Install ArgoCD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### 3. Deploy the ArgoCD Application
```bash
kubectl apply -f platform/argocd/apps/sample-app.yaml
```

### 4. Use devctl to Scaffold New Service
```bash
bash tools/devctl.sh create-service my-new-service
```

### 5. Use ChatGPT for AI Assistance
- Ask ChatGPT to explain `deployment.yaml`
- Use prompts in `docs/ai-prompts.md`

---

## 🧠 Resources
- [`docs/architecture.md`](docs/architecture.md) – High-level system design
- [`docs/golden-paths.md`](docs/golden-paths.md) – Recommended developer flows
- [`docs/ai-prompts.md`](docs/ai-prompts.md) – Useful prompts for AI copilots

---

## 🙌 Author
Bob Adewusi
- GitHub: [@Bobaddey](https://github.com/Bobaddey)
- Twitter: [@BobTechies](https://twitter.com/BobTechies)
