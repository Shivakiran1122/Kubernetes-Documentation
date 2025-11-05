kubectl : 
-----------------------------------------------------------------------------------------------------------------------

kubectl is the command-line tool used to interact with a Kubernetes cluster.

It lets you deploy, manage, and troubleshoot Kubernetes resources like Pods, Deployments, and Services.

-----------------------------------------------------------------------------------------------------------------------
🧩 What You Can Do with kubectl
-----------------------------------------------------------------------------------------------------------------------

Create and manage resources – Create, update, or delete Pods, Deployments, and Services.

Monitor resources – View cluster status, Pod details, and node information.

Troubleshoot – Check logs, describe resources, or run commands inside containers.

Node operations – Cordon, drain, or delete cluster nodes when needed.

-----------------------------------------------------------------------------------------------------------------------
🔧 Common kubectl Commands
-----------------------------------------------------------------------------------------------------------------------

Command	Description :

kubectl get pods	Lists Pods in the cluster

kubectl create -f file.yaml	Creates resources from a YAML file

kubectl apply -f file.yaml	Updates or applies configuration

kubectl delete pod <name>	Deletes a specific resource

kubectl logs <pod>	Shows logs from a Pod

kubectl exec -it <pod> -- /bin/bash	Opens a shell inside a running container
-----------------------------------------------------------------------------------------------------------------------
🚀 Why kubectl is Important
-----------------------------------------------------------------------------------------------------------------------

Central management – Acts as the main interface between you and the Kubernetes API server.

Troubleshooting tool – Helps inspect and debug applications and nodes.

Automation – Used in scripts and CI/CD pipelines for automated deployments.

-----------------------------------------------------------------------------------------------------------------------
 kubectl Interacts with Kubernetes Components (Simplified Technical Flow)
-----------------------------------------------------------------------------------------------------------------------

kubectl is a client tool that communicates with the Kubernetes API Server, which is the central control point of the cluster.

Through the API Server, kubectl can create, update, or retrieve information about cluster resources like Pods, Deployments, and 

Services.

-----------------------------------------------------------------------------------------------------------------------
🧩 Key Interactions
-----------------------------------------------------------------------------------------------------------------------

API Server – kubectl sends REST API requests here.

The API Server validates the requests, updates the cluster state, and coordinates actions with other components.

etcd – The API Server stores and retrieves all cluster data from etcd, which acts as Kubernetes’ database.

Scheduler – When a new Pod is created, the API Server informs the Scheduler to select a suitable node.

Kubelet – Once the Scheduler assigns a node, the API Server instructs the Kubelet (on that node) to start the containers.

Container Runtime – The Kubelet then interacts with the runtime (like Docker or containerd) to run the actual container.

-----------------------------------------------------------------------------------------------------------------------
🔁 Sequence Flow (Command → Container)
-----------------------------------------------------------------------------------------------------------------------

User → kubectl: You run a command, e.g., kubectl get pods or kubectl apply -f app.yaml.

kubectl → API Server: The command is sent as a REST request to the API Server.

API Server → etcd: The API Server retrieves or updates the cluster state in etcd.

API Server → Scheduler: For new Pods, it requests scheduling on an available node.

Scheduler → API Server: The Scheduler reports which node was chosen.

API Server → Kubelet: Instructs the Kubelet on that node to start or manage the Pod.

Kubelet → Container Runtime: The Kubelet calls Docker/containerd to create or run containers.

-----------------------------------------------------------------------------------------------------------------------
🔄 Response Flow (Container → User)
-----------------------------------------------------------------------------------------------------------------------

Container → Kubelet: Sends status updates.

Kubelet → API Server: Reports back container and Pod status.

API Server → etcd: Updates the cluster’s stored state.

API Server → kubectl: Sends the result of your request.

kubectl → User: Displays the information or confirmation.

-----------------------------------------------------------------------------------------------------------------------
🗣️ Final Summary
-----------------------------------------------------------------------------------------------------------------------

1. kubectl is a command-line tool that talks to the Kubernetes API Server, which is the core of the control plane.

2. When I run a command like kubectl get pods, kubectl sends a REST request to the API Server.

3. The API Server validates it, retrieves data from etcd, and sends it back.

4. For creation commands, it coordinates with the Scheduler to place Pods on nodes and with the Kubelet to run containers through the container runtime.

5. So kubectl itself doesn’t control the cluster — it interacts with the API Server, which in turn manages all the components.”