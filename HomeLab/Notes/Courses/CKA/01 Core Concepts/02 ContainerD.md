## Crictl vs Docker

### ### Retrieve debugging information [](https://k8s.aluopy.cn/docs/reference/tools/map-crictl-dockercli/#retrieve-debugging-information)

| Docker CLI | Crictl  | Description                                                     | Unsupported Features                |
| ---------- | ------- | --------------------------------------------------------------- | ----------------------------------- |
| attach     | attach  | attach to running container                                     | --detach-keys, --sig-proxy          |
| exec       | exec    | Run a command in a running container                            | --privileged, --user, --detach-keys |
| images     | images  | List images                                                     |                                     |
| info       | info    | Display system-wide information                                 |                                     |
| inspect    | inspect | Return low level information on a container, image or task      |                                     |
| logs       | logs    | Fetch the logs of a container                                   | --details                           |
| ps         | ps      | List containers                                                 |                                     |
| status     | status  | Display a live stream of container(s) resource usage statistics | Column: NET/BLOCK I/O, PIDs         |
| version    | version | show the runtime (Docker, ContainerD, etc.) version information |                                     |                                                              |                                     |

### ### Perform Changes [](https://k8s.aluopy.cn/docs/reference/tools/map-crictl-dockercli/#perform-changes)

| docker cli | crictl               | Description                                    | Unsupported Features                                                              |
| ---------- | -------------------- | ---------------------------------------------- | --------------------------------------------------------------------------------- |
| `create`   | `create`             | Create a new container                         |                                                                                   |
| `kill`     | `stop` (timeout = 0) | Kill one or more running container             | `--signal`                                                                        |
| `pull`     | `pull`               | Pull an image or a repository from a registry  | `--all-tags`, `--disable-content-trust`                                           |
| `rm`       | `rm`                 | Remove one or more containers                  |                                                                                   |
| `rmi`      | `rmi`                | Remove one or more images                      |                                                                                   |
| `run`      | `run`                | Run a command in a new container               |                                                                                   |
| `start`    | `start`              | Start one or more stopped containers           | `--detach-keys`                                                                   |
| `stop`     | `stop`               | Stop one or more running containers            |                                                                                   |
| `update`   | `update`             | Update configuration of one or more containers | `--restart`, `--blkio-weight` and some other resource limit not supported by CRI. |

### Supported only in crictl[](https://k8s.aluopy.cn/docs/reference/tools/map-crictl-dockercli/#supported-only-in-crictl)

| crictl         | Description                            |
| -------------- | -------------------------------------- |
| `imagefsinfo`  | Return image filesystem info           |
| `inspectp`     | Display the status of one or more pods |
| `port-forward` | Forward local port to a pod            |
| `pods`         | List pods                              |
| `runp`         | Run a new pod                          |
| `rmp`          | Remove one or more pods                |
| `stopp`        | Stop one or more running pods          |

### crt vs nerdctl vs crictl 

| ctr | nerdctl | crictl |
| --- | --- | --- |
| **Purpose** | Debugging | General Purpose| Debugging |
| **Community** | ContainerD | ContainerD | Kubernetes |
| **Works With** | ContainerD | ContainerD | All CRI Compatible |

Next:
[[Notes/Courses/CKA/01 Core Concepts/03 ETCD]]

Previous:
[[Notes/Courses/CKA/01 Core Concepts/01A Control Plane Components]]
