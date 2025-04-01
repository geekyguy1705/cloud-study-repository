### kube-apiserver[](https://kubernetes.io/docs/concepts/architecture/#kube-apiserver)

The API server is a component of the Kubernetes [control plane](https://kubernetes.io/docs/reference/glossary/?all=true#term-control-plane) that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.

### etcd[](https://kubernetes.io/docs/concepts/architecture/#etcd)

Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.

### kube-scheduler[](https://kubernetes.io/docs/concepts/architecture/#kube-scheduler)

Control plane component that watches for newly created [Pods](https://kubernetes.io/docs/concepts/workloads/pods/) with no assigned [node](https://kubernetes.io/docs/concepts/architecture/nodes/), and selects a node for them to run on.

### kube-controller-manager[](https://kubernetes.io/docs/concepts/architecture/#kube-controller-manager)

Control plane component that runs [controller](https://kubernetes.io/docs/concepts/architecture/controller/) processes.

Logically, each [controller](https://kubernetes.io/docs/concepts/architecture/controller/) is a separate process, but to reduce complexity, they are all compiled into a single binary and run in a single process.

There are many different types of controllers. Some examples of them are:

- Node controller
- Job controller
- EndpointSlice controller
- ServiceAccount controller

### cloud-controller-manager[](https://kubernetes.io/docs/concepts/architecture/#cloud-controller-manager)

A Kubernetes [control plane](https://kubernetes.io/docs/reference/glossary/?all=true#term-control-plane) component that embeds cloud-specific control logic. The cloud controller manager lets you link your cluster into your cloud provider's API, and separates out the components that interact with that cloud platform from components that only interact with your cluster.

The following controllers can have cloud provider dependencies:

- Node controller: For checking the cloud provider to determine if a node has been deleted in the cloud after it stops responding
- Route controller: For setting up routes in the underlying cloud infrastructure
- Service controller: For creating, updating and deleting cloud provider load balancers

Next:
[[Notes/Courses/CKA/01 Core Concepts/01B Node Components]]

Previous: 
[[Notes/Courses/CKA/01 Core Concepts/01 Kubernetes Cluster Architecture]] 

