Kubernetes CLI Cheat sheet

```bash
# Show join token
kubeadm token create --print-join-command

# List current resources
kubectl api-resourcess

# Running Commands in a Container
kubectl exec -i​t <Pod-Name> -- /bin/bash

# View the events for a particular pod
kubectl describe pod try1-76cc5ffcc6-tx4dz | tail

# View status of a particular pod
kubectl describe pod try1-76cc5ffcc6-tx4dz | grep -E 'State|Ready'

```