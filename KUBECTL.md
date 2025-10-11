# kubectl Quick Reference
### Export useful variables
```
alias k=kubectl
export dry='--dry-run=client -o=yaml'
export oy='-o=yaml'
alias kn='kubectl config set-context --current --namespace '
export ETCDCTL_API=3
```

### Context and configuration

```
# Show Merged kubeconfig settings.
kubectl config view

# Show merged kubeconfig settings and raw certificate data and exposed secrets
kubectl config view --raw

# Display list of contexts
kubectl config get-contexts

# Display the current-context
kubectl config current-context

# switch to another namespace in the current context.
kubectl config set-context --current --namespace=development

# Delete user 'foo' from the current context.
kubectl config unset users.foo
```

### Creating objects

```
# apply multiple manifests
kubectl apply -f ./manifest1.yaml ./manifest2.yaml

# apply all manifest files in a directory
kubectl apply -f ./dir

# apply a manifest file from a URL
kubectl apply -f https://example.com/manifest.yaml

# create a deployment named 'nginx' using the nginx:alpine image with 2 replicas
kubectl create deployment nginx --image=nginx:alpine --replicas=2

# run a pod named 'ubuntu' using the ubuntu image and keep it running
kubectl run ubuntu --image=ubuntu sleep infinity

# generate a Pod manifest for a web server and save it to nginx-pod.yaml (dry run)
kubectl run web-server --image=nginx:stable-alpine --port=80 --dry-run=client -o yaml | tee nginx-pod.yaml

# explain the restartPolicy field in the Pod spec
kubectl explain pod.spec.restartPolicy

# create a Job which prints "Hello World"
kubectl create job hello --image=busybox:1.28 -- echo "Hello World"

# create a CronJob that prints "Hello World" every minute
kubectl create cronjob hello --image=busybox:1.28   --schedule="*/1 * * * *" -- echo "Hello World"
```

### Interacting with running Pods

```
# dump pod logs (stdout)
kubectl logs my-pod

# dump pod logs (stdout) for a previous instantiation of a container
kubectl logs my-pod --previous

# dump pod container logs (stdout, multi-container case)
kubectl logs my-pod -c my-container

# dump pod container logs (stdout, multi-container case) for a previous instantiation of a container
kubectl logs my-pod -c my-container --previous

# stream pod logs (stdout)
kubectl logs -f my-pod

# stream pod container logs (stdout, multi-container case)
kubectl logs -f my-pod -c my-container

# stream all pods logs with label name=myLabel (stdout)
kubectl logs -f -l name=myLabel --all-containers

# Run pod as interactive shell
kubectl run -it busybox --image=busybox:1.28 -- sh

# Listen on port 5000 on the local machine and forward to port 6000 on my-pod
kubectl port-forward my-pod 5000:6000

# Run command in existing pod (1 container case)
kubectl exec my-pod -- ls /

# Run command in existing pod (multi-container case)
kubectl exec my-pod -c my-container -- ls /

# Show metrics for all pods in the default namespace
kubectl top pod

# Show metrics for a given pod and sort it by 'cpu' or 'memory'
kubectl top pod POD_NAME --sort-by=cpu
```
