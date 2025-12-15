# Commands:

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

- **cmd5: kubectl run pod_name --image=nginx:latest** 
  - o/p: 
    - pod/nginx-pod created.
  - purpose:
    - To create pod in imperative way.

- **cmd6: kubectl get pods** 
  - o/p: 
    - NAME        READY   STATUS    RESTARTS   AGE
      nginx-pod   1/1     Running   0          59s
  - purpose:
    - List the pods.

- **cmd7: kubectl explain pod** 
  - o/p: 
    - KIND:       Pod
      VERSION:    v1
      DESCRIPTION:
      FIELDS:
          apiVersion    <string>
          kind  <string>
          metadata      <ObjectMeta>
          spec  <PodSpec>
          status        <PodStatus>

- **cmd8: kubectl create/apply -f pod.yaml** 
  - o/p: 
    - pod/nginx-pod created.
  - purpose:
    - To create pod.

- **cmd8: kubectl delete pod pod_name** 
  - o/p: 
    - pod "nginx-pod" deleted.
  - purpose:
    - To delete a pod.

- **cmd9: kubectl describe pod pod_name** 
  - o/p: 
    - Name:             nginx-pod
      Namespace:        default
      Priority:         0
      Service Account:  default
      Node:             dora-cluster-worker2/172.18.0.4
      Start Time:       Fri, 12 Dec 2025 22:54:01 +0530.....
  - purpose:
    - To debug the issue in the pod.

- **cmd10: kubectl edit pod pod_name** 
- o/p: 
    - pod/nginx-pod edited
  - purpose:
    - To edit the configurations on the running pod

- **cmd11: kubectl exec -it pod_name -- sh** 
- o/p: 
    - ls
      bin   dev                  docker-entrypoint.sh  home  media  opt   product_uuid  run   srv  tmp  var
      boot  docker-entrypoint.d  etc                   lib   mnt    proc  root          sbin  sys  usr
  - purpose:
    - To enter within the container.

- **cmd12: kubectl run nginx --image=nginx --dry-run=client -o yaml > pod_new.yaml** 
- o/p: 
    - A new pod yaml file.
  - purpose:
    - A new pod yaml file that can be updated with required changes and then applied.
