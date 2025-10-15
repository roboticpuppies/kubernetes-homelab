# Ingress NGINX

## How to install

If you use Minikube, install NGINX ingress by running `minikube addon enable ingress` instead.

```bash
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace infrastructure
```
*[Ingress NGINX quick start](https://kubernetes.github.io/ingress-nginx/deploy/#quick-start)*