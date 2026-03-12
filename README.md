# Devops Learning Task

This repository is meant for me to keep track of my progress in learning DevOps
from the ground up.

> [!WARNING]
> Since this repo is meant to evolve organically just like my own knowledge, do
> some things in here might not make any sense structurally.

## Learning progress

### Kubernetes Fundamentals

Everything I currently know about kubernetes.

- [x] Understanding what is and how kubernetes works
- [x] Deploying a simple application (without YAML manifest)
- [x] Understanding what are Kubernetes API Objects
- [x] Running workloads in pods
    - [x] Running an application by creating a pod from a YAML manifest
    - [x] Interacting with the application, viewing its logs, and exploring its environment
    - [x] Understanding what is a sidecar container
    - [x] Understanding what are init containers
- [x] Managing the pod lifetime
    - [x] Inspecting the pod status
    - [x] Probes
        - [x] Liveness probe
        - [x] Startup probe
    - [x] Understanding about a pod's phase, condition and status
- [x] Volumes
    - [x] How to persist files across container restarts
    - [x] How to share files between containers of the same pod
    - [x] How to share files between pods
    - [x] What are external volumes and its caveats
    - [x] What is a `hostPath` volume type and why it is so dangerous
