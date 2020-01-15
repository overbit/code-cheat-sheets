# Kubernetes CLI Cheat sheet

## CLI tips

```bash
# alias and autocomplete alias
alias kn='kubectl config set-context --current --namespace '
alias k=kubectl
source <(kubectl completion bash | sed 's/kubectl/k/g')
```

```bash
# Monitor cluster
watch -n 0.5 "kubectl config current-context; echo ''; kubectl config view | grep namespace; echo ''; kubectl get namespace,node,ingress,pod,svc,job,cronjob,deployment,rs,pv,pvc,secret,ep -o wide"
```

## kubectl

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

### Deployment

```bash
# Create deployment imperatively
kubectl create deployment try1 --image=10.110.186.162:5000/simpleapp:latest
```

### Rollout / rollback

```bash
# Rollout new image for deployment (record allow annotation in the resource file)
kubectl set image deployment/<deployment-name>  <container-name>=<image:version> --record

# Check history
kubectl rollout history deployment <deployment-name>

# Rollback to previous state
kubectl rollout undo deployment <deployment-name>

kubectl rollout undo deployment <deployment-name> --to-revision=<number>
```
