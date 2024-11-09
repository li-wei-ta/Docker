# ETCD

- **Definition** - A distributed reliable key-value store that is Simple, Secure & Fast
- Stores information about the cluster such as Nodes, PODS, Configs, Secrets, Accounts, Roles, Bindings, Others
- Only once the changes are made in the etcd server, is the change considered to be complete
- When you run an ETCD service `./etcd`, it starts a service that **listens on port 2379 by default**
- `etcdctl` client is the default client, it is the command line used to interact with etcd database
  - To store a key value pair -> `./etcdctl set key1 value1`
  - To view a key value -> `./etcdctl get key1`
- ETCD version

  - How to check the version `./etcdctl --version`
  - Newer version in `v3` the command to set a value is now `./etcdctl put key1 value`
  - With the release of version 3.4 the default API version is set to 3
  - To change etcdctl to work with `v3`, there are two ways to set it:
    - `ETCDCTL_API=3 ./etcdctl version`
    - `export ETCDCTL_API=3 ./etcdctl version`

- Depending on how your kubernetes is deployed, etcd is also deployed differently, Two types of Kubernetes Deployment
  - Deployed from scratch
    - `wget -q --https-only <url for the etc binary>`
  - Deployed using the kubeadm tool
    - kubeadm it deploys the etcd server as a **pod in the kubeadm namespace**
    - `kubectl get pods -n kube-system`
