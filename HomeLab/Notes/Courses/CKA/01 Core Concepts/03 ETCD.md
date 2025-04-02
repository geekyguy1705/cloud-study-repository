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


## Some ETCD Commands

ETCDCTL can interact with ETCD Server using 2 API versions - Version 2 and Version 3.  By default its set to use Version 2. Each version has different sets of commands.  

For example ETCDCTL version 2 supports the following commands:
1. etcdctl backup
2. etcdctl cluster-health
3. etcdctl mk
4. etcdctl mkdir
5. etcdctl set

Whereas the commands are different in version 3:
1. etcdctl snapshot save 
2. etcdctl endpoint health
3. etcdctl get
4. etcdctl put

  
To set the right version of API set the environment variable ETCDCTL_API command

`export ETCDCTL_API=3`

#Note : When API version is not set, it is assumed to be set to version 2. And version 3 commands listed above don't work. When API version is set to version 3, version 2 commands listed above don't work.

Apart from that, one must also specify path to certificate files so that ETCDCTL can authenticate to the ETCD API Server. The certificate files are available in the etcd-master at the following path. -
1. --cacert /etc/kubernetes/pki/etcd/ca.crt     
2. --cert /etc/kubernetes/pki/etcd/server.crt     
3. --key /etc/kubernetes/pki/etcd/server.key

  

So for the commands above to work one must specify the ETCDCTL API version and path to certificate files. Below is the final form:  
- `kubectl exec etcd-master -n kube-system -- sh -c "ETCDCTL_API=3 etcdctl get / --prefix --keys-only --limit=10 --cacert /etc/kubernetes/pki/etcd/ca.crt --cert /etc/kubernetes/pki/etcd/server.crt  --key /etc/kubernetes/pki/etcd/server.key"`


Next:
[[Notes/Courses/CKA/01 Core Concepts/04 KubeAPI Server]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/02 ContainerD]]