# Kube scheduler

- ONLY responsible for which pod goes on which nodes it doesn't actually deploy pods on the nodes (That would be the kublet)
- When a new pod is created, the scheduler looks at the available nodes and picks the **most suitable** node based on a bunch of criteria
- Process/workflow:

  1. Evaluate the node sustainability, such as CPU, Memory, Taints and tolerance, node affinity
  2. After the filtering is done, it assigns scores on all the nodes(based on criteria) and picks the best one
  3. It assigns the pod to the best node and let the kublet take over

- View api-server - kubeadm
  - `kubectl get pods -n kube-system`
- View api-server - non kubeadm
  - `cat /etc/systemd/system/kube-scheduler.service`
- View running process
  - `ps -aux | grep kube-scheduler`
