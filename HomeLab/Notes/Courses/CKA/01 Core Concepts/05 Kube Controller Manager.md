## What is kube-controller-manager?

The Kubernetes controller manager is a daemon that embeds the core control loops shipped with Kubernetes. 
In Kubernetes, a controller is a control loop that watches the shared state of the cluster through the apiserver and makes changes attempting to move the current state towards the desired state. 

Examples of controllers that ship with Kubernetes today are the **replication** controller, **endpoints** controller, **namespace** controller, and **serviceaccounts** controller, etc.

## How to intall kube-controller-manager?

1. download binary, extract it and use it as a service.

#Note: When kube-controller-manager is used as a service there are various options provided which can be customized. Eg. `--node-monitor-period=5s`, `--node-monitor-grace-period=40s`, `--pod-eviction-timeout=5m0s`, etc. 

#Note: `--controllers stringslice     Default: [\*] `
	Above flag can be used to enable/disable controllers. By default all the controllers are enabled.

## How to view kube-controller-manager options?
- For kubeadm setup -
	- `cat /etc/kubernetes/manifests/kube-controller-manager.yaml`
- For non-kubeadm setup -
	- `cat /etc/systemd/system/kube-controller-manager.service`
- To view running process and the options and values set -
	- `ps -aux | grep kube-controller-manager`

Next:
[[06 Kube Scheduler]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/04 KubeAPI Server