## Objective
The Node `node01` is not yet part of the cluster, join it using kubeadm.

## Clue

Need to generate the join token. Then connect the `node01` to the control-plane using the token and the join command.
```bash
kubeadm token -h
```