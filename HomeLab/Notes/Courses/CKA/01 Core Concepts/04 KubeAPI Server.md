## What is KubeAPI server

The Kubernetes API server validates and configures data for the api objects which include pods, services, replicationcontrollers, and others. The API Server services REST operations and provides the frontend to the cluster's shared state through which all other components interact.

## How is a new pod request handled

1. User requests using API instead of CLI (Eg. curl -X POST /api/v1/namespaces/default/pods/...)
2. KubeAPI server authenticates user and then validates request. In this case, KubeAPI server
	1. creates a pod object without assigning it to a node, 
	2. updates the information in the etcd cluster and 
	3. updates the user that the pod is being created.
3. Scheduler monitors the KubeAPI server and realizes that there is a new pod without node assigned.
4. It then identifies the right node to schedule the pod on and communicates that back to the  KubeAPI server and KubeAPI server then updates the etcd cluster.
5. KubeAPI server then passes that information to the kubelet in the appropriate worker node
6. Kubelet creates the pod on the node and instructs the container runtime engine (CRE) to deploy the application image.
7. Once done, kubelet informs back to the KubeAPI server and KubeAPI server then updates the data back in the etcd cluster. 
8. Similar pattern is followed every time a change is requested.

#Note : KubeAPI server is responsible for the following - It is central to all the actions that happen in the Kubernetes cluster.
1. Authenticate User
2. Validate Request
3. Retrieve data
4. Update ETCD
5. Scheduler
6. Kubelet


Next:
[[Notes/Courses/CKA/01 Core Concepts/05 Kube Controller Manager]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/03 ETCD]]