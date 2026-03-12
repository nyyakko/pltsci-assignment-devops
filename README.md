# Devops Learning Task

This repository is meant for me to keep track of my progress in learning DevOps
from the ground up.

> [!WARNING]
> Since this repo is meant to evolve organically just like my own knowledge,
> some things in here might not make any sense structurally.

## Learning progress

### Kubernetes Fundamentals

Everything I currently know about kubernetes.

- [x] Understanding what is and how kubernetes works
- [x] Simple application deployment (without YAML manifest)
- [x] Kubernetes API Objects
- [x] Pods
    - [x] Workloads
        - [x] Running an application by creating a pod from a YAML manifest
        - [x] Interacting with the application, viewing its logs, and exploring its environment
        - [x] Understanding what is a sidecar container
        - [x] Understanding what are init containers
    - [x] Lifetime
        - [x] Inspecting the pod status
        - [x] Probes
            - [x] Liveness probe
            - [x] Startup probe
        - [x] Understanding about a pod's condition, phase and status
- [x] Volumes
    - [x] How to persist files across container restarts
    - [x] How to share files between containers of the same pod
    - [x] How to share files between pods
    - [x] What are external volumes and its caveats
    - [x] Security implications of a `hostPath` volume
- [x] Persistent Volumes
    - [x] Persistent Volumes Claim
    - [x] Sharing volumes between pods
    - [x] Access modes
