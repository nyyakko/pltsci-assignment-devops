# Devops Learning Task

This repository is meant for me to keep track of my progress in learning DevOps
from the ground up.

> [!WARNING]
> Since this repo is meant to evolve organically just like my own knowledge,
> some things in here might not make any sense structurally.

> [!NOTE]
> Yes I know about the cert and the private key. They are worthless, thou
> shan't be worried.

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
        - Understanding about a pod's condition, phase and status
        - Inspecting the pod status
        - Probes
            - Liveness probe
            - Startup probe
        - Lifecycle
            - postStart
            - preStop
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
    - Downward API
    - Projected Volume
* Organizing Objects
    - Namespaces
        - Setting a default namespace to work with `kubectl`
    - Labels
        - Label selectors
            - Equality based
            - Set based
    - Field selectors
    - Annotations
- Services
    - Pod networks are linked via a flat network
    - Interacting with cluster-internal pods
        - Resolving services with the internal dns server
    - Service Types
        - ClusterIP
        - NodePort
        - LoadBalancer
            - Makes it so an actual LoadBalancer is provisioned in the cluster (if supported)
    - The externalTrafficPolicy field
    - External services
    - Endpoints
    - Headless services
    - The internalTrafficPolicy field
    - Topology-aware routing
    - Readiness probes
- Ingress
    - Ingress Object
    - Ingress Controller
    - Reverse Proxy (L7 Load Balancer)
        - How the proxy forwards traffic to the services it backs
    - Resolving a service by its host name
        - Through cURL
        - Through the browser
    - Path matching (Exact vs Prefix)
    - Host field wildcard
    - Default backend
    - TLS
        - By forwading to the pod's sidecar container
            - Non-standard, uses annotations and depends on the ingress controller being used
        - By handling it directly in the ingress
    - Additional configuration may be done either by
        - Using annotations
        - Using custom api objects
    - IngressClass can be used to
        - Specify the ingress controller responsible for creating an ingress through ingressClasName
        - Give additional parameters to the ingress controller
    - Custom resources may be used as backends
- ReplicaSets
    - Why use a ReplicaSet?
    - The caveats of using ReplicaSets directly
    - Scaling ReplicaSets

### Observability

Everything I currently know about system monitoring and observability.

- Observability Basics
    - Pillars of Observability
        - Logs
        - Traces
        - Metrics
    - What is system monitoring
- Monitoring Tools
    - Prometheus
        - Basic node monitoring with node_exporter
    - Grafana
        - Visualizing metrics from Prometheus
        - Consuming pre-built dashboards for K8S cluster monitoring

