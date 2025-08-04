# Kubernetes RBAC

**RBAC** stands for **Role-Based Access Control**. It is a way to control who can do what in your Kubernetes cluster. RBAC helps keep your cluster secure by making sure people only have the access they need.

- **Role**: A set of permissions (like "can read pods" or "can create deployments"). Usually scoped into namespaces.
- **RoleBinding**: Connects a Role to a user or group, giving them those permissions.
- **ClusterRole**: Like a Role, but applies to the whole cluster.
- **ClusterRoleBinding**: Connects a ClusterRole to a user or group for the whole cluster.

## ClusterRole Exercise

1. Create a read-only ClusterRole named `cluster-viewer` in `cluster-role.yaml`.
2. Bind that ClusterRole into a Group named `cluster-viewer` in `cluster-role-binding.yaml`
3. Create a user called `luna` that will be a member of `cluster-viewer` group. Let's create the private key first.
   ```
   openssl genrsa -out luna.key 4096
   ```
4. Then generate CSR before signing the key.
   ```
   openssl req -new -key luna.key -out luna.csr -subj "/CN=luna/O=viewer" -sha256
   ```
5. Encode the CSR and put it inside variable called `CSR_DATA`.
   ```
   CSR_DATA=$(base64 luna.csr | tr -d '\n')
   ```
6. Create a certificate signing request using the `luna-csr.yaml` as reference. The CSR_DATA is needed in the `.spec.request` field.
7. You can approve the signing request by running `kubectl certificate approve luna-csr`.
8. Now you can see the certificate data (base64 encoded) by running `kubectl get csr luna-csr -o jsonpath='{.status.certificate}'`. This data will be used as the client-certificate in the kubeconfig file. The luna.key will be used as client-key.