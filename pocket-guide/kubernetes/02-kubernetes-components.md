# Kubernetes Components

\* Useful summary of [Kubernetes Components](https://kubernetes.io/docs/concepts/overview/components/)

Binary components:

- Master Components
- Node Components

## Master Components

### kube-apiserver

- Kubernetes API
- Front-end for the Kubernetes control plane

### etcd

- Consistent and highly-available **key value store** used as Kubernetes's backing store for all cluster data

### kube-scheduler

- Watches newly created pods that have no node assigned and selects a node for them to run on

### kube-controller-manager

Runs controllers:

- **Node Controller**: Responsible for noticing and responding when nodes go down
- **Replication Controller**: Responsible for maintaining the correct number of pods for every replication controller object in the system.
- **Endpoints Controller**: Populates the Endpoints object (that is, join Services & Pods).
- **Service Account & Token Controllers**: Create default accounts and API access tokens for new namespaces

## Node Components

Run on every node, maintaining running pods and providing the Kubernetes runtime environment.

![node](https://d33wubrfki0l68.cloudfront.net/5cb72d407cbe2755e581b6de757e0d81760d5b86/a9df9/docs/tutorials/kubernetes-basics/public/images/module_03_nodes.svg)

### kubelet

- An agent that makes sure that containers are running in a pod (and healthy).

### kube-proxy

- Network proxy
- Maintains network rules on nodes (in-and-out internet connection)

### Container Runtime

- Responsible for running containers.
- [Docker](http://www.docker.com/), [containerd](https://containerd.io/), [cri-o](https://cri-o.io/), [rktlet](https://github.com/kubernetes-incubator/rktlet)
