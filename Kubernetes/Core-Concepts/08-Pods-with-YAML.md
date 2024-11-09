# YAML in kubernetes

- e.g. structure of a yaml file for deploying a pod
- Root level properties and require fields:
  - `apiVersion` (string) -> Defines the version of the api server
  - `kind` (string) -> The type of project that we are trying to create (Pod, Service, ReplicaSet, Deployment)
  - `metadata`(dictionary) -> data about the object (like tags to help grouping the pods together -> frontend) and can have any custom key value pair the user want to put
  - `spec` (list) ->
- **pod-definition.yml** example:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-prod
  labels:
    app: myapp
    type: front-end
spec:
  containers:
    - name: nginx-container
      image: nginx
```

- Command to run the configuration and therefore run the pod
  - `kubectl create -f pod-definition.yml`
- Getting description of the pod
  - `kubectl describe pod myapp-pod`
