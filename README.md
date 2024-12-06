# Kubernetes Homelab

This repository is used to keep my homelab manifest. Mostly I use it for testing and learning Kubernetes.

## Prepare the environment

I usually use Minikube. Run this command to start the cluster:

```bash
# Start a minikube single node with 6gb memory. The profile is named 'Viper'
minikube start --memory 6g -p viper
```

The applications will be deployed to the `app` namespace.

```bash
# Create namespace for the apps
kubectl create ns app
```

## Directory tree

```bash
.
├── README.md
├── chart # A helm chart to deploy the application
├── grafana # Store the values for Grafana chart
├── istio # Store the values for Istio chart
└── prometheus  # Store the values for Prometheus chart
```