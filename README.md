# GitOps: Argo CD Deployment for Hash Store

This repository manages GitOps-based deployment of the `hash-store` Helm chart using Argo CD and Kustomize.

---

## Structure

```text
.
├── hash-store/
│   ├── Chart.yaml           # Chart metadata
│   ├── values.yaml          # Default configuration values
│   ├── templates/           # Kubernetes manifests
│   │   ├── _helpers.tpl     # Template helper definitions
│   │   ├── deployment.yaml  # Deployment manifest
│   │   ├── ingress.yaml     # Ingress manifest
│   │   ├── service.yaml     # Service manifest
├── .github/
│   └── workflows/
│       └── Helm-package.yaml # CI pipeline to package and push Helm chart
├── README.md                # Project documentation

```
---

## 🚀 App of Apps - Argo CD

This repository implements the **App of Apps** pattern for [Argo CD](https://argo-cd.readthedocs.io), allowing you to manage and deploy multiple Kubernetes applications from a single manifest.

---

## 📦 What’s Deployed?

- A single Argo CD `Application` named **`app-of-apps`**
- This application references a directory (`apps/`) that contains child applications
- One of the child applications deploys the **`hash-store`** Helm chart to the **`rigetti-demo`** namespace





