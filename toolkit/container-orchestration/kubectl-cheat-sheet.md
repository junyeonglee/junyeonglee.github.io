# kubectl Cheat Sheet

My most common `kubectl` command\
Reference: [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

```bash
# Config
kubectl config use-context my-cluster-name # set the default context to my-cluster-name
kubectl config set-context my-cluster-name --namespace=my-namespace # set the default context to my-cluster-name with specified my-namespace

# Creating Objects
kubectl apply -f ./my-manifest.yaml # create resource(s)
kubectl apply -f ./dir # create resource(s) in all manifest files in dir

# Get commands with basic output
kubectl get services # List all services
kubectl get pods # List all pods
kubectl get deployments # List all deployments

# Describe commands with verbose output
kubectl describe pod my-pod

# Interacting with running Pods
kubectl exec -it my-pod bash # Run pod(my-pod) as interactive shell
kubectl run -it ubuntu --image=ubuntu -- bash # Run pod(ubuntu) as interactive shell
kubectl logs -f my-pod # stream pod logs (stdout)
kubectl logs -f -l name=myLabel --all-containers # stream all pods logs with label name=myLabel (stdout)

# Scaling Resources
kubectl scale --replicas=2 deployment/foo # Scale a deployment named 'foo' to 2

# Deleting Resources
kubectl delete deployment my-deployment # Delete deployment
kubectl delete pod my-pod # Delete pod

# Formatting output
-o=json # Output a JSON formatted API object
-o=yaml # Output a YAML formatted API object
```
