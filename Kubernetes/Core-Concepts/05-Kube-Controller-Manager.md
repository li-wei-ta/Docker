# Kube Controller Manager

- Responsible for **on going maintenance** of the **desired state** across the entire cluster
- Think of it as the brain of the architecture that keeps monitoring if the current state matches the desired state
- Does this through a multiple different controllers, each responsible for a specific type of resource in the cluster:

  - **Node Controller** -> Monitors the health of the Nodes, and responds when a node go down or becomes unhealthy
  - **Replication Controller** -> Ensures that the desired number of replicas are running in the cluster
  - **Endpoint Controller** -> Manages endpoints objects that connect services to pods
  - There are many more

- View api-server - kubeadm
  - `kubectl get pods -n kube-system`
- View api-server - non kubeadm
  - `cat /etc/systemd/system/kube-controller-manager.service`
- View running process
  - `ps -aux | grep kube-controller-manager`
