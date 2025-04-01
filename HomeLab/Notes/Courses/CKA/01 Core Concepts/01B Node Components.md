
### kubelet[](https://kubernetes.io/docs/concepts/architecture/#kubelet)

An agent that runs on each [node](https://kubernetes.io/docs/concepts/architecture/nodes/) in the cluster. It makes sure that [containers](https://kubernetes.io/docs/concepts/containers/) are running in a [Pod](https://kubernetes.io/docs/concepts/workloads/pods/).

### kube-proxy (optional)[](https://kubernetes.io/docs/concepts/architecture/#kube-proxy)

kube-proxy is a network proxy that runs on each [node](https://kubernetes.io/docs/concepts/architecture/nodes/) in your cluster, implementing part of the Kubernetes [Service](https://kubernetes.io/docs/concepts/services-networking/service/) concept.

[kube-proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/) maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.

kube-proxy uses the operating system packet filtering layer if there is one and it's available. Otherwise, kube-proxy forwards the traffic itself.

If you use a [network plugin](https://kubernetes.io/docs/concepts/architecture/#network-plugins) that implements packet forwarding for Services by itself, and providing equivalent behavior to kube-proxy, then you do not need to run kube-proxy on the nodes in your cluster.

### Container runtime[](https://kubernetes.io/docs/concepts/architecture/#container-runtime)

A fundamental component that empowers Kubernetes to run containers effectively. It is responsible for managing the execution and lifecycle of containers within the Kubernetes environment.




Next:
[[Notes/Courses/CKA/01 Core Concepts/01C Addons]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/01A Control Plane Components]]
