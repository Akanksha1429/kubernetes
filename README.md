# Kubernetes

### What is K8s:

  1. Container Orchestration platform
  2. Cluster Architecture
  3. Autohealing(Control & fix damage)
  4. Autoscaling
  5. Enterprise Support

### Architecture:
![K8s architecture](</images/architecture.png>)

### Commands:
- **cmd1: kubectl cluster-info --context name_of_the_cluster** 
  - o/p: 
    - Kubernetes control plane is running at https://127.0.0.1:51632
    - CoreDNS is running at https://127.0.0.1:51632/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
  - purpose:
    - shows cluster endpoints (API server, DNS, other core services) for the given kubeconfig context.

- **cmd2: kubectl get nodes** 
  - o/p: 
    - NAME                 STATUS   ROLES           AGE   VERSION
      kind-control-plane   Ready    control-plane   18m   v1.34.0
  - purpose:
    - List the nodes present in the cluster.(request -> api-server -> validation and authentication -> fetching data from **ETCD** -> reply with the nodes that are running.)

- **cmd3: kubectl config get-context**                                                   
  - purpose:
    - list all the clusters available.

- **cmd3: kubectl config set-context kind-dora-cluster** 
  - o/p: 
    - Context "kind-dora-cluster" modified.

- **cmd4: kubectl config use-context kind-dora-cluster** 
  - o/p: 
    - Switched to context "kind-dora-cluster".