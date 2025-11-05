# 🚀 Kubernetes in One Shot

This repository is a **comprehensive one-shot guide** to Kubernetes — covering everything from **core concepts** to **advanced operations**.  
It organizes real-world `kubectl` commands into clear categories so you can **learn, practice, and revise** Kubernetes efficiently.

---

## 📘 Table of Contents
1. [Core Concepts](#-core-concepts)
2. [Setup (Local / AWS EC2)](#-setup-local--aws-ec2)
3. [Kubectl and Pods](#-kubectl-and-pods)
4. [Namespaces, Labels, and Annotations](#-namespaces-labels-and-annotations)
5. [Workloads](#-workloads)
6. [Networking](#-networking)
7. [Storage](#-storage)
8. [ConfigMaps and Secrets](#-configmaps-and-secrets)
9. [Scaling and Scheduling](#-scaling-and-scheduling)
10. [Cluster Administration](#-cluster-administration)
11. [Monitoring and Logging](#-monitoring-and-logging)
12. [Advanced Features](#-advanced-features)
13. [Security](#-security)
14. [Cloud-Native Kubernetes](#-cloud-native-kubernetes)
15. [Debugging and Troubleshooting](#-debugging-and-troubleshooting)
16. [Summary](#-summary)
17. [Author](#-author)

---

## 🧠 Core Concepts

**Monolithic vs Microservices, Kubernetes Architecture**
```bash
kubectl cluster-info
```
Displays cluster information to understand the Kubernetes architecture.

---

## ⚙️ Setup (Local / AWS EC2)

```bash
kind create cluster --name=tws-cluster --config=config.yml
kubectl config use-context kind-tws-cluster
```
Create and configure a local Kubernetes cluster using **Kind**.

---

## 🧩 Kubectl and Pods

```bash
kubectl get nodes
kubectl run nginx --image=nginx -n nginx
kubectl describe pod nginx -n nginx
```
List nodes, deploy an Nginx Pod, and inspect Pod details.

---

## 🗂️ Namespaces, Labels, and Annotations

```bash
kubectl create namespace monitoring
kubectl get namespace
kubectl label namespace monitoring team=devops
kubectl describe namespace monitoring
```
Create and organize namespaces for resource isolation.

---

## 🧱 Workloads

### Deployments
```bash
kubectl apply -f deployment.yml
kubectl scale deployment nginx-deployment --replicas=3 -n nginx
```

### StatefulSets
```bash
kubectl apply -f statefulset.yml
kubectl describe statefulset mysql -n database
```

### DaemonSets
```bash
kubectl apply -f daemonset.yml
kubectl describe daemonset fluentd -n logging
```

### ReplicaSets
```bash
kubectl apply -f replicaset.yml
kubectl describe replicaset nginx-replicaset -n nginx
```

### Jobs & CronJobs
```bash
kubectl apply -f job.yml
kubectl apply -f cronjob.yml
```

---

## 🌐 Networking

### Cluster Networking
```bash
kubectl get svc -A
```

### Services
```bash
kubectl apply -f service.yml
kubectl describe svc nginx-service -n nginx
```

### Ingress
```bash
kubectl apply -f ingress.yml
kubectl describe ingress nginx-ingress -n nginx
```

### Network Policies
```bash
kubectl apply -f networkpolicy.yml
```

---

## 💾 Storage

### Persistent Volumes (PV) & Persistent Volume Claims (PVC)
```bash
kubectl apply -f persistentVolume.yml
kubectl apply -f persistentVolumeClaim.yml
```

### Storage Classes
```bash
kubectl get storageclass
```

---

## ⚙️ ConfigMaps and Secrets

```bash
kubectl create configmap app-config --from-file=config.properties
kubectl create secret generic db-credentials --from-literal=username=admin --from-literal=password=admin123
```
Manage configuration data and sensitive credentials securely.

---

## 📈 Scaling and Scheduling

### HPA / VPA
```bash
kubectl autoscale deployment nginx --cpu-percent=50 --min=1 --max=10 -n nginx
kubectl apply -f vpa.yml
```

### Node Affinity / Taints / Tolerations
```bash
kubectl taint nodes node1 key=value:NoSchedule
kubectl apply -f node-affinity.yml
```

### Resource Quotas, Limits, and Probes
```bash
kubectl apply -f resourcequota.yml
kubectl describe quota my-quota -n dev
```

---

## 🧑‍💼 Cluster Administration

### RBAC (Roles & RoleBindings)
```bash
kubectl apply -f role.yml
kubectl apply -f rolebinding.yml
```

### Custom Resource Definitions (CRDs)
```bash
kubectl apply -f crd.yml
kubectl get crd
```

---

## 📊 Monitoring and Logging

### Metrics Server
```bash
kubectl apply -f metrics-server.yml
kubectl top node
```

### Prometheus and Grafana
```bash
helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring
kubectl port-forward svc/prometheus-stack-grafana 3000:80 -n monitoring --address=0.0.0.0
```

---

## 🧩 Advanced Features

### Helm
```bash
helm create my-chart
helm install my-app my-chart -n my-namespace --create-namespace
```

### Sidecar & Init Containers
```bash
kubectl apply -f init-container.yml
kubectl apply -f sidecar-container.yml
```

---

## 🔐 Security

```bash
kubectl apply -f podsecuritypolicy.yml
kubectl apply -f secrets-encryption.yml
```
Apply Pod Security Policies and enable Secret encryption.

---

## ☁️ Cloud-Native Kubernetes

### Managed Services (EKS, AKS, GKE)
```bash
eksctl create cluster --name my-cluster
```

### Cluster Autoscaler
```bash
kubectl apply -f cluster-autoscaler.yml
```

---

## 🧰 Debugging and Troubleshooting

```bash
kubectl logs pod-name -n namespace
kubectl describe pod pod-name -n namespace
kubectl exec -it pod-name -n namespace -- bash
```
Inspect logs, describe resources, and access running containers interactively.

---

## 🏁 Summary

This repository brings together **all major Kubernetes concepts and commands** in one place —  
from setup and deployment to scaling, networking, and monitoring.  

> 📘 Ideal for: **Beginners, DevOps learners, and professionals revising Kubernetes fundamentals.**

---

## ✨ Author

**Shiva Kiran Dadishetty**  
💻 *DevOps & MLOPS Enthusiast*  

---