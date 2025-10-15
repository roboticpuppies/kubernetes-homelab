# My Namespaces

## Overview

Honestly, I don't know the best practices for using namespaces yet. For example, should I create separate namespaces for ArgoCD, CNPG, NGINX Ingress, and so on? So, I've grouped all these components into a namespace called `infrastructure`.

All example applications will be deployed in the `production` namespace. And for some reason I put the monitoring system, e.g., Grafana, and Prometheus, into the `monitoring` namespace.