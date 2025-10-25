## Objective


## Clue
### Workflow
```mermaid
flowchart TD
    A([SSH into the machine])-->B(Check etcd pod status)
    B-->C(Describe etcd pod to get config)
    C-->D(Get --listen-client-urls for the endpoint url)
    D-->E(Get --cert-file for server certificate location)
    E-->F(Get --trusted-ca-file for CA certificate location)
    F-->G(etcdctl snapshot save)
    G-->H([Exit the machine])
```

### How-to
```bash
# get the etcd details
kubectl get pods -n kube-system
kubectl describe pod etcd-xxx -n kube-system
ETCDCTL_API=3 etcdctl --cacert=xxxx \
    --cert=xxx \
    --key=xxx \
    snapshot save /opt/etcd-backup.db
```

## References
- [Backing up an etcd cluster](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/#built-in-snapshot)