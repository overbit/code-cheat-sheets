Kubernetes CLI Cheat sheet

```bash
# Show join token
kubeadm token create --print-join-command

# List current resources
kubectl api-resourcess

# Running Commands in a Container
kubectl exec -i​t <Pod-Name> -- /bin/bash
```