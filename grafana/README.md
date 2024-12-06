# Grafana Server

## Up and Running

```bash
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update

helm install grafana grafana/grafana -n monitoring --create-namespace -f values.yaml
```