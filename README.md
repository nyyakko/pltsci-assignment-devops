# Devops Learning Task

This repository is meant for me to keep track of my progress in learning DevOps
from the ground up.

> [!WARNING]
> Since this repo is meant to evolve organically just like my own knowledge,
> some things in here might not make any sense structurally.

## Learning progress

### Kubernetes Fundamentals

Everything I currently know about kubernetes.

- Understanding what is and how kubernetes works
- Simple application deployment (without YAML manifest)
- Kubernetes API Objects
- Pods
    - Workloads
        - Running an application by creating a pod from a YAML manifest
        - Interacting with the application, viewing its logs, and exploring its environment
        - Understanding what is a sidecar container
        - Understanding what are init containers
    - Lifetime
        - Inspecting the pod status
        - Probes
            - Liveness probe
            - Startup probe
        - Understanding about a pod's condition, phase and status
- Volumes
    - How to persist files across container restarts
    - How to share files between containers of the same pod
    - What are external volumes and its caveats
    - Security implications of a `hostPath` volume
- Volumes Provisioning
    - Access modes
    - Static Provisioning
        - Persistent Volume Claim
            - How to persist files across pod restarts
            - How to share files between pods
            - Sharing volumes between pods
        - Lifetime of a statically provisioned persistent volume
        - Local persistent volumes
    - Dynamic Provisioning
        - Storage Classes
        - Dynamic Volume Expansion
        - Lifetime of a dynamically provisioned persistent volume
- Configuring Pods
    - Environment variables
    - ConfigMap
        - ConfigMap Volumes
        - Ceveats when updating ConfigMap files
    - Secrets
