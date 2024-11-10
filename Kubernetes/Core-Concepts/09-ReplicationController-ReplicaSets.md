# Replication Controller

- **Purpose** - Manages a specific desired number of identical pods replicas, ensuring that desired state is maintained by creating or deleting pods
  - **High availability**
  - **Load Balancing & Scaling**
- It is currently being replaced by the newer version **Replica Set**
- e.g structure of replication controller
  - `template` (under `spec`)
    - Under here we define the template for the kind of container we would want to replicate
    - Therefore, we use the template that defined the pods
  - `replicas` -> desired number of replicas needed

```yaml

apiVersion: v1
kind: Replication Controller
metadata:
  name: myapp-rc
  labels:
    app: my-app
    type: front-end

spec:
  - template:
        metadata:
        name: myapp-prod
        labels:
            app: myapp
            type: front-end
        spec:
        containers:
            - name: nginx-container
            image: nginx
  - replicas: 3

```

- create the replication controller:
  `kubectl create -f rc-controller.yaml`
- get the replication controller:
  `kubectl get replicationcontroller`

# Replica Set

- Newer, and generally preferred in newer setups
- Difference:
  - apiVersion -> apps/v1
  - **selector** -> Basically a way to group pods together and tells the replica set which group to monitor
- e.g.

```yaml

apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: myapp-replicaset
  labels:
    app: my-app
    type: front-end

spec:
  - template:
        metadata:
        name: myapp-prod
        labels:
            app: myapp
            type: front-end
        spec:
        containers:
            - name: nginx-container
            image: nginx
  - replicas: 3
  - selector:
        matchLabels:
            type: front-end
```

- create the replica set:
  `kubectl create -f replicaset-definition.yaml`
- get the replica set:
  `kubectl get replicaset`

### Scale methods

- Replace the number of `replicas` in the file iteself then run
  - `kubectl replace -f replicaset-definition.yaml`
- Pass it in as a parameter
  - `kubectl scale --replicas=6 -f replicaset-definition.yaml`
  - Note however, that the definition file still does not change if you use this method
