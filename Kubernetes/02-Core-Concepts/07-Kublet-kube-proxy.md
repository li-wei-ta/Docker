# Kublet

- 'Captain' of the ship (worker nodes)
- Manages the **lifecycle** of the pods on that node
  - Pulling images and starting containers
  - Health monitoring and reporting of those containers
- Communicates with the API server to ensure that the pods meets the specifications (aka PodSpecs)
- Works with **Container runtime** (Docker, containerd, etc)

  - Uses CRI (Container runtime interface) to **abstract** away differences in container runtimes

- View running process
  - `ps -aux | grep kube-scheduler`

# Kube Proxy

- Within a kubernetes cluster every pod can communicate with every other pod, it is known as the **Pod network**
- For each of those pods we need a set of rules to assign to them, this is where kube proxy comes in
- **Each pod has it's own corresponding kube proxy**
- Think of it as a set of rules that defines
- Used for:

  1. Pod to Pod communication
  2. External client-to-service communication
  3. Service discovery and Load balancing

- View api-server - kubeadm
  - `kubectl get pods -n kube-system`
  - Deamon Set
    - `kubectl get deamonset -n kube-system`
