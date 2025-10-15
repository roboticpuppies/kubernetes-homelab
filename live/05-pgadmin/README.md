# CloudNativePG

## How to install

```bash
helm repo add runix https://helm.runix.net
helm install pgadmin4 runix/pgadmin4 \
  --namespace infrastructure \
  -f values.yaml
```
*[PGAdmin4 Helm chart](https://artifacthub.io/packages/helm/runix/pgadmin4)*