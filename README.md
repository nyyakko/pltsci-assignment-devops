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
    - The reconciliation loop
        - Pods whose containers continously crash or fail their probes are
          never deleted automatically
    - Debugging a pod controller by a ReplicaSets
- Deployments
    - Why use a Deploment?
    - Updating a deployment
        - Deployment strategies
            - Recreate
            - RollingUpdate
            - Canary
            - A/B Testing
            - Blue/Green
            - Shadowing
        - Pausing the update
    - Availability

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

### AWS

Everything I currently know about cloud computing on AWS.

- What is the cloud
    - What is cloud computing
    - Why do we need cloud computing
    - Terms
        - Region
        - Availability Zone
        - Scalability
        - Elasticity
- IAM
    - Roles
    - Policies
- EC2
    - Basics
        - How to create a simple instance
        - Connecting through SSH
    - Security Groups
    - Instance Types
        - General Purpose
        - Compute Optimized
        - Storage Optimized
        - Memory Optimized
        - HPC Optimized
    - Purchasing Options
        - On-Demand
        - Reserved (Depecrated in favor of Savings Plan)
        - Spot Instances
        - Dedicated Hosts
        - Dedicated Instances
    - Networking
        - Elastic vs Public vs Private IP
        - Elastic Network Interface (ENI)
    - Placement Groups
        - Cluster
            - Caveats to consider when using a Cluster PG
        - Spread
        - Partition
    - Amazon Machine Image (AMI)
    - Storing Data
        - Encryption
        - Snapshots
        - Multi Attach
        - Volume Types
            - General Purpose (gp)
            - Provisioned IOPS (io)
            - Cold HDD (sc)
            - Throughput Optimized HDD (st)
        - EFS vs EBS
- ELB
    - Basics
        - What is a load balancer
        - Why use a load balancer
        - Liveness
            - Healthy Checks
    - Load Balancer Types
        - Classic Load Balancer (HTTP, HTTPS, TCP, SSL)
        - Application Load Balancer (HTTP, HTTPS, WebSocket)
            - Operates at the application level
            - Good for microservices
            - Special Headers
                - X-Forwarded-For (holds the ip of the client)
                - X-Forwarded-Port (holds the port used in the connection)
                - X-Forwarded-Proto (holds the protocol used in the connection)
        - Network Load Balancer (TCP, TLS)
            - Extremely high performance (handles many requests per second)
            - One ip per availability zone (AZ)
            - A network load balancer target group can be an
                - ec2 instance
                - ip address (must be private)
                - application load balancer
        - Getaway Load Balancer
            - Operates at the network level
            - Good for packet analysis, firewall, prevention systems, etc
            - A getaway load balancer target group can be an
                - ec2 instance
                - ip addresses (must be private)
    - Sticky Sessions (Session Affinity)
        - Types of cookies for affinity
            - Application-based cookie
                - Generated by the application
            - Duration-based cookie
                - Generated by the load balancer
    - Cross-Zone Load Balancing
    - SSL/TLS
        - Server Name Indication (SNI)
            - Used to indicate which certificate is the right one for the domain
            - Only works on ALB and NLB
    - Connection Draining (or Deregistration Delay)
    - Auto Scaling Group (ASG)
        - Scaling policies
            - Dynamic Scaling
                - Simple Scaling Policy
                - Target Tracking Policy
                - Step Scalling Policy
            - Scheduled Scaling
            - Predictive Scaling
