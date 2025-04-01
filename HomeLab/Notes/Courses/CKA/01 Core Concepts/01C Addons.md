## Addons[](https://kubernetes.io/docs/concepts/architecture/#addons)

Addons use Kubernetes resources ([DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset), [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/), etc) to implement cluster features. Because these are providing cluster-level features, namespaced resources for addons belong within the `kube-system` namespace.

Selected addons are described below; for an extended list of available addons, please see [Addons](https://kubernetes.io/docs/concepts/cluster-administration/addons/)

### DNS[](https://kubernetes.io/docs/concepts/architecture/#dns)

While the other addons are not strictly required, all Kubernetes clusters should have [cluster DNS](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/), as many examples rely on it.

Cluster DNS is a DNS server, in addition to the other DNS server(s) in your environment, which serves DNS records for Kubernetes services.

Containers started by Kubernetes automatically include this DNS server in their DNS searches.

### Web UI (Dashboard)[](https://kubernetes.io/docs/concepts/architecture/#web-ui-dashboard)

[Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) is a general purpose, web-based UI for Kubernetes clusters. It allows users to manage and troubleshoot applications running in the cluster, as well as the cluster itself.

### Container resource monitoring[](https://kubernetes.io/docs/concepts/architecture/#container-resource-monitoring)

[Container Resource Monitoring](https://kubernetes.io/docs/tasks/debug/debug-cluster/resource-usage-monitoring/) records generic time-series metrics about containers in a central database, and provides a UI for browsing that data.

### Cluster-level Logging[](https://kubernetes.io/docs/concepts/architecture/#cluster-level-logging)

A [cluster-level logging](https://kubernetes.io/docs/concepts/cluster-administration/logging/) mechanism is responsible for saving container logs to a central log store with a search/browsing interface.

### Network plugins[](https://kubernetes.io/docs/concepts/architecture/#network-plugins)

[Network plugins](https://kubernetes.io/docs/concepts/extend-kubernetes/compute-storage-net/network-plugins/) are software components that implement the container network interface (CNI) specification. They are responsible for allocating IP addresses to pods and enabling them to communicate with each other within the cluster.

Next:
[[Notes/Courses/CKA/01 Core Concepts/02 ContainerD]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/01A Control Plane Components]]
