# CloudNativePG

## How to install

These commands will install CloudNativePG in the `infrastructure` namespace and then create a new Cluster, databases, and connection pooler in the `production` namespace for the example-apps.

```bash
helm repo add cnpg https://cloudnative-pg.github.io/charts
helm upgrade --install cnpg \
  --namespace infrastructure \
  cnpg/cloudnative-pg
kubectl apply -f example-app-db.yaml
```
*[CloudNativePG quick start](https://cloudnative-pg.io/documentation/current/quickstart/)*