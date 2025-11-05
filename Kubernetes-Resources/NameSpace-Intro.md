
Namespace in Kubernetes : 
-----------------------------------------------------------------------------------------------------------------------

A namespace in Kubernetes is a way to divide a cluster into logical sections.

It helps you organize and isolate resources (like Pods, Services, and Deployments) within the same cluster.

Think of a namespace like a folder in your computer —

you can have files (Pods, Services) with the same name in different folders (namespaces) without conflict.

-----------------------------------------------------------------------------------------------------------------------
🧩 Why Namespaces Are Useful
-----------------------------------------------------------------------------------------------------------------------

Resource Isolation — Different teams or projects can use their own namespaces without affecting each other.

Access Control — You can apply RBAC (Role-Based Access Control) rules per namespace to manage permissions.

Resource Quotas — You can limit CPU, memory, or storage usage within each namespace.

Organization — Helps manage large clusters by grouping related resources together.
-----------------------------------------------------------------------------------------------------------------------

📦 Default Namespaces
-----------------------------------------------------------------------------------------------------------------------

Kubernetes comes with a few predefined namespaces

Namespace	               Purpose

default	                  Used when no other namespace is specified.

kube-system	              Contains system components (like kube-dns, scheduler, controller-manager).

kube-public	              Used for publicly accessible resources.

kube-node-lease	          Stores heartbeats of nodes for faster node failure detection.
-----------------------------------------------------------------------------------------------------------------------
🔧 Common kubectl Commands
-----------------------------------------------------------------------------------------------------------------------

Command	Description

kubectl get namespaces	Lists all namespaces in the cluster

kubectl create namespace dev	Creates a new namespace

kubectl get pods --namespace=dev	Lists Pods inside the “dev” namespace

kubectl delete namespace dev	Deletes a namespace and its resources

-----------------------------------------------------------------------------------------------------------------------
🗣️ Final Summary 
-----------------------------------------------------------------------------------------------------------------------

1. A namespace in Kubernetes is used to logically separate and organize cluster resources.

2. It allows multiple teams or environments — like dev, test, and prod — to share the same cluster without interfering with each other.

3. Each namespace has its own set of Pods, Services, and resource quotas.

4. By default, Kubernetes creates namespaces like default, kube-system, and kube-public.

5. I can create my own namespace using kubectl create namespace <name> and view resources inside it using the --namespace flag.