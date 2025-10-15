# ArgoCD

## How to install

ArgoCD is installed into `infrastructure` namespace.

```bash
helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd argo/argo-cd -n infrastructure -f values.yaml

# Get the default admin password
kubectl -n infrastructure get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```
*[ArgoCD Installation](https://argo-cd.readthedocs.io/en/stable/operator-manual/installation/#helm)*