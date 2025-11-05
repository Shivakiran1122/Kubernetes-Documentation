Kubernetes Pod : 
-----------------------------------------------------------------------------------------------------------------------

A Pod is the smallest deployable unit in Kubernetes.

It acts as a wrapper around one or more containers that are tightly coupled and need to share resources.

Containers inside the same Pod share the same IP address, network namespace, and storage, so they can talk to each other directly using localhost.

Most of the time, a Pod has a single container, but sometimes it can have a sidecar container — for example, a logging or monitoring agent that works alongside the main application container.

Pods are ephemeral, meaning if a Pod fails, Kubernetes automatically replaces it through a Deployment or ReplicaSet to maintain the desired state.

-----------------------------------------------------------------------------------------------------------------------
🧠 How a Pod Is Created and Runs
-----------------------------------------------------------------------------------------------------------------------

You create a Pod definition in a YAML file (e.g., pod.yaml).

You run:

kubectl apply -f pod.yaml

The API Server stores the Pod definition in etcd (Kubernetes’ database).

The Scheduler decides which Node should run the Pod.

The Kubelet on that Node pulls the container image and runs it using the container runtime (like Docker or containerd).

The Pod gets its own IP address, and Services use that IP to route traffic to the Pod.

-----------------------------------------------------------------------------------------------------------------------
🧩 Useful kubectl Commands
-----------------------------------------------------------------------------------------------------------------------

Command	Description:

kubectl get pods	Lists all Pods in the current namespace

kubectl describe pod <pod-name>	Shows detailed information about a specific Pod

kubectl apply -f pod.yaml	Creates or updates a Pod from a YAML file

-----------------------------------------------------------------------------------------------------------------------
🗣️ Final Summary
-----------------------------------------------------------------------------------------------------------------------

1. In Kubernetes, a Pod is the smallest unit that can be deployed.

2. It’s basically a wrapper around one or more containers that share the same IP address, network, and storage.

3. Most Pods have a single container, but we can also have a sidecar container for tasks like logging.

4. Pods are short-lived — if one dies, Kubernetes recreates it automatically.

5. When I create a Pod using kubectl apply -f pod.yaml, the API Server stores it in etcd, the Scheduler assigns it to a Node, and the Kubelet pulls the image and runs the container.

6. I can check Pods using commands like kubectl get pods or kubectl describe pod <pod-name>.”
