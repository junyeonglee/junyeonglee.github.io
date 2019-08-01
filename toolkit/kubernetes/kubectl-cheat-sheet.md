# kubectl Cheat Sheet

My most common `kubectl` command\
Reference: [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

```bash
# Get commands with basic output
kubectl get pods # List all pods
kubectl get deployments # List all deployments

# Interacting with running Pods
kubectl exec -it my-pod bash # Run pod(my-pod) as interactive shell
kubectl run -it ubuntu --image=ubuntu -- bash # Run pod(ubuntu) as interactive shell

# Deleting Resources
kubectl delete deployment stupid-deployment # Delete deployment(stupid-deployment)
```
