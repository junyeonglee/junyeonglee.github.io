# Kubernetes: Concepts

\* Useful summary of [Concepts](https://kubernetes.io/docs/concepts/)

## Overview

**Kubernetes API**: Describe cluster's desired state (workloads, replicas, network, etc...), typically via the command-line interface, `kubectl`

**Kubernetes Control Plane** :

- The **Kubernetes Master** is a collection of three processes (**kube-apiserver**, **kube-controller-manager** and **kube-scheduler**) that run on a single node in your cluster, which is designated as the master node.

- Each individual non-master node in your cluster runs two processes:
  - **kubelet**, which communicates with the Kubernetes Master.
  - **kube-proxy**, a network proxy which reflects Kubernetes networking services on each node.

## Kubernetes Objects

The basic:

- Pod
- Service
- Volume
- Namespace

In addition, Controllers(build upon the basic objects with additional functionality and convenience features):

- ReplicaSet
- Deployment
- StatefulSet
- DaemonSet
- Job

## Kubernetes Control Plane

- Respond to changes in the cluster.
- Work to make the actual state of all the objects in the system match the desired state.

### Kubernetes Master

- Maintains the desired state of cluster
- Used by `kubectl` CLI
- Controls each node

### Kubernetes Nodes

- Machines (VMs, physical servers, etc) that run applications and cloud workflows

Here's the architecture of a Kubernetes cluster:

![kubernetes-cluster-architecture](https://d33wubrfki0l68.cloudfront.net/e298a92e2454520dddefc3b4df28ad68f9b91c6f/70d52/images/docs/pre-ccm-arch.png)

Next: [What is Kubernetes](01-what-is-kubernetes.md)
