# Prometheus Server

## Up and Running

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm install prometheus prometheus-community/prometheus -n monitoring --create-namespace --version 27.3.1 -f values.yaml
```

## Changing the configurations

Edit the `values.yaml` then apply it:

```bash
helm upgrade prometheus prometheus-community/prometheus -n monitoring --version 27.3.1 -f prometheus/values.yaml
```