# Logs

### Docker

- `docker run kodekloid/event-simulator`
  - It generates random events simulating a web server
- `docker run -d kodekloud/event-simulator`
  - You won't see the logs
- `docker run -f <container id>`
  - Gives us container's live log trail

### Kubernetes

- Just like in kubernetes when we run:
  - `k logs -f <pod name>`
  - Stream the log live
- If there are multiple container in a pod then you run:
  - `k logs -f <pod name> <container name>`
