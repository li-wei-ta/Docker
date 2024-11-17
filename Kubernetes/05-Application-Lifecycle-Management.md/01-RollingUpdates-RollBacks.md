# Rollout and Versioning

- Creating a deployment -> Triggers a rollout -> creates a new revision (basically a version)
- When container updated -> Triggers a new rollout -> creates a new revision

![alt text](./images/image.png)

- Rollout command
  - `k rollout status deployment/myapp-deployment` -> status of rollouts
  - `k rollout history deployment/myapp-deployment` -> history of rollouts

# Deployment Strategy

- **Recreate**
  - Destroy all the containers
  - Relaunch all the containers
  - CONS -> There is an application down time
- **Rolling update** -> Default deployment strategy

  - Take down an old one, replace with new one
  - One by one

- How to update/upgrade:
  ![alt text](./images/image_1.png)

  ![alt text](./images/image_2.png)

  ![alt text](./images/image_3.png)
