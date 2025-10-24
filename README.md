# Kubernetes Homelab

This repository is used to keep my homelab manifest. Mostly I use it for testing and learning Kubernetes.

## Prepare the environment

I usually use Minikube. Run this command to start the cluster:

```bash
# Start a minikube single node with 6gb memory.
minikube start --memory 6g
```

## Directory tree

```bash
.
├── README.md
├── KUBECTL.md # Kubectl cheatsheet
├── learning # For me to learn and test kubernetes basics
└── live # Kubernetes manifests that have been running in my homelab
```

## Todo

Will complete the list and details later.

[v] Ingress NGINX
[v] CloudNativePG
[v] ArgoCD
[v] PgAdmin
[] KEDA
[] API Gateway
[] Monitoring stack
[] Redis
[] Deploy microservice example app
[] Vault