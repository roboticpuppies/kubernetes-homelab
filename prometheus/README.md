# Prometheus Server

## Up and Running

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm install prometheus prometheus-community/prometheus -n monitoring --create-namespace -f values.yaml
```