```bash
# https://artifacthub.io/packages/helm/cert-manager/cert-manager
helm repo add jetstack https://charts.jetstack.io --force-update
helm install cert-manager --namespace cert-manager --create-namespace --version v1.17.1 jetstack/cert-manager -f cert-manager/values.yml
```