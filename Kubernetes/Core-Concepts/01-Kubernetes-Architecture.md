# Kubernetes Architecture

### Control (Master Node) - Manage, Plan, Schedule, Monitor Nodes

- Kube-APIserver -> Accepting and processing api requests
- etcd -> Key-value store that holds the cluster data
- Controller manager -> Ensure the cluster state matches the desired configuration
- Kube-Scheduler -> Scheduling workloads onto nodes based on available resources

### Nodes (Worker Nodes) - Host Applications as Containers

- Kubelet (Captain of the ship) -> main node agent that receives and executes pods instructions from control plane, managing the lifecycle of containers on the node
- Kube-proxy -> Manages networking of the nodes, ensuring pods to communicate with each other where needed
- Container runtime -> Responsible for running the containers specified in each pod (e.g. Docker, containerd or CRI-O)
