
Kubernetes Architecture
-----------------------------------------------------------------------------------------------------------------------

Kubernetes architecture is built around two main parts — the Control Plane and the Worker Nodes — that work together to manage and run containers.
-----------------------------------------------------------------------------------------------------------------------
🧠 1. Control Plane (Master Node)
-----------------------------------------------------------------------------------------------------------------------

The control plane manages the overall cluster and makes decisions about scheduling and scaling.

It includes:

API Server – The main entry point; it exposes the Kubernetes API and handles all requests (from kubectl or other services).

Scheduler – Decides which node a Pod should run on, based on resource availability.

Controller Manager – Watches the cluster’s state and ensures the desired state matches the actual state (e.g., if a Pod fails, it creates a new one).

etcd – (You can mention this too) It’s the key-value database that stores all cluster data and configurations.

-----------------------------------------------------------------------------------------------------------------------
💻 2. Worker Nodes
-----------------------------------------------------------------------------------------------------------------------

These are the machines that actually run your application containers.

Each worker node has:

Kubelet – An agent that talks to the control plane and ensures containers are running as defined in the Pod specs.

Kube-proxy – Manages networking and load balancing so that Pods can communicate internally and externally.

Container runtime – The software (like Docker or containerd) that actually runs the containers.
-----------------------------------------------------------------------------------------------------------------------
📦 3. Pods and Services
-----------------------------------------------------------------------------------------------------------------------

Pod – The smallest deployable unit in Kubernetes. It can contain one or more containers that share the same network and storage.

Service – Provides a stable IP and DNS name to access Pods, even if Pods move or restart.
-----------------------------------------------------------------------------------------------------------------------
🔄 4. How Components Work Together
-----------------------------------------------------------------------------------------------------------------------

A user sends a deployment or Pod creation request to the API Server.

The API Server validates and stores the request in etcd.

The Scheduler picks a suitable node to run the Pod.

The Kubelet on that node creates and monitors the containers.

The Kube-proxy manages network rules and routes traffic to the correct Pod.
-----------------------------------------------------------------------------------------------------------------------
🗣️Final Summary
-----------------------------------------------------------------------------------------------------------------------

1. Kubernetes architecture is divided into a control plane and worker nodes.

2. The control plane has components like the API server, scheduler, controller manager, and etcd, which handle all cluster management and decisions.

3. The worker nodes run the actual containers using kubelet, kube-proxy, and a container runtime.

4. When I deploy an app, the API server receives the request, the scheduler assigns it to a node, and the kubelet starts the containers.

Overall, Kubernetes ensures that my application always runs as desired — automatically managing scaling, recovery, and networking.