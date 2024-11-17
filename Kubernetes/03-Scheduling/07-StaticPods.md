# Static Pods

- Stand alone Node that is managed by the kublet
- Pods definition files are USUALLY defined under the `etc/kubernetes/manifests`
- Since there is no kube api server -> There is no **kubectl utility** -> therefore use docker
- The **kubectl** api is only allowed a **READ ONLY** Access to the pods
- To modify the static pods itself you would have to:
  - ssh into the node -> `ssh <node name>`
  - find the directory where the config file is stored:
    - `ps -ef |grep /usr/bin/kubelet`
    - `grep -i staticpod /var/lib/kubelet/config.yaml`
  - Modify/delete the config file to reflect any changes
