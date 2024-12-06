# Istio Service Mesh and Gateway

## Up and Running

```bash
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
helm install istiod istio/istiod --namespace istio-system --create-namespace -f values.yaml
```