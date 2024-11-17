# Multiple Scheduler

- Allows running multiple schedulers (custom) to handle different scheduling requirements
- Default Scheduler -> `kube-scheduler-controlplane`
- During pod creation you can add which scheduler for the pod to be scheduled with by adding `schedulerName` parameter under `spec`
- How do you knoow which scheduler scheduled which pod?
  - `k get events -o wide`
- view logs of scheduler
  - `k logs my-custom-scheduler`
