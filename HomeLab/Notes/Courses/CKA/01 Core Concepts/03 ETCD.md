## All the basics about ETCD

- **etcd** is a distributed reliable key-value store that is Simple, Secure and Fast.
- **etcd** runs on port 2379
- **Installation**: Download Binary --> extract it --> go to folder and run etcd with ./etcd
- Use ./etcdctl to store and retrieve key-value pairs
- Eg.
	- ./etcdctl get key1
	- ./etcdctl put key1 value1
	- ./etcdctl --version
	- etc.

## ETCD in Kubernetes

- Stores information about the cluster such as -
	- Nodes
	- Pods
	- Configs
	- Secrets
	- Accounts
	- Roles
	- Bindings
	- Others
	- Every Change done to nodes, pods, configs, etc is updated in the etcd db. Only after it is updated in the ETCD, the change is considered to be complete.
	- Kubeadm deploys etcd database as a pod in the kube-system namespace and can be accessed using etcdctl inside the etcd-master pod
	- ETCD in HA environment - initial cluster configuration needs information about all the etcd instances. Examples of HA Kubernetes cluster setups - ![[02 Kubeadm HA topology - stacked etcd.png| Kubeadm HA topology - stacked etcd]] ![[03 Kubeadm HA topology - external etcd.png| Kubeadm HA topology - external etcd]]




Next:
[[Notes/Courses/CKA/01 Core Concepts/04]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/02 ContainerD]]