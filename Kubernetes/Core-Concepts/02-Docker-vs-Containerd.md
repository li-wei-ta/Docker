# Docker vs Containerd

### Docker

- Initially Docker was used as the main container runtime by Kubernetes
- However it Docker was more of a monolithic application
- It had a lot of non-essential features that was not required to just run an application (such as image building, docker deamon, etc)
- Additionally, as Kubernetes gained popularity they introduced CRI (Container runtime interface), to make all container platform runtime compatible with kubernetes
- However, Docker didn't really directly comform to these standards that's where Containerd came in

### Containerd

- More modular, lightweight version of Docker
- It included only the key essential features of running an container, NOT for building images
- It was more kubernetes compatible

### ctr, nerdctl, crictl

- ctr
  - Purpose: A low-level CLI for containerd.
  - Use Case: Directly interacts with containerd for container and image management but has limited usability, as it’s intended mainly for containerd developers and troubleshooting.
  - Characteristics: Not user-friendly; lacks Docker-like commands and is primarily used for internal containerd operations.
- nerdctl

  - Purpose: A Docker-compatible CLI for containerd.
  - Use Case: Provides Docker-style commands (e.g., run, build, pull) directly on containerd, enabling familiar workflows without Docker.
  - Characteristics: Aimed at users who want Docker-like functionality on containerd without needing Docker itself; suitable for general container management, especially in non-Kubernetes environments.

- crictl
  - Purpose: A Kubernetes-native CLI for managing CRI-compliant runtimes.
  - Use Case: Used for debugging and managing containers and pods within Kubernetes environments by interacting with CRI endpoints.
  - Characteristics: Provides Kubernetes-specific commands (e.g., crictl ps, crictl logs), focused solely on CRI-compliant runtimes (like containerd or CRI-O) for troubleshooting Kubernetes nodes.
