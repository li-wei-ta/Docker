# OS updates

- `k drain <node name>`
  - pods are terminated in that node and recreated in other nodes
  - Ensures that no pods can be scheduled to that node
- `k uncordon <node name>`
  - When it comes back online again, still no pods can be scheduled to it
  - To "uncordon" it means to open it up for being scheduled again
- `k cordon <node name>`
  - When you just restrict it from being scheduled
