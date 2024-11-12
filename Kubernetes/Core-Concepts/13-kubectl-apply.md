# Kubectl apply

- Declarative approach to resource management
- Similar idea as terraform state files
- Three way merge strategy
  - **Last-applied state** -> last configuration applied to the resource
    - Mainly used for figuring out what configuration has been removed
  - **Current state/Live object configuration** -> The current state of the resource
  - **Desired state** -> desired state defined in the manfiest file
