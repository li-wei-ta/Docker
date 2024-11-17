# Monitor Cluster Components

- Used for monitoring the cluster

  - Number or nodes in the cluster
  - Performance metrics -> CPU, Memory, etc

- Kubernetes does not have a built in monitoring solutions
- Open sourced solutions:

  - Metric Service
  - Prometheus
  - Elastic Stack

- Heapster is depricated -> new one is Metrics server

### Metrics Server

- Responsible for storing **in memory** metrics not for historical logging

#### How does Node communicate with Metric server?

- Kubelet -> cAdvisor

### Commands

- `k top node` -> nodes with highest resource consumptions
- `k top pod` -> performance metrics of pods
