### Cluster management system

### Key insights
- General purpose cluster management system

### Architecture
![Docker](/images/kubernetes.jpg)

0. Master.
    - Apiserver. Entry of k8s. Use restful to communicate.
    - Scheduler. Cluster resource management.
    - Control management. replication -> 3 times.
    - Etcd. Storage information of cluster (key-value) !Raft algorithm to guarantee the consitency.

1. Node.
    - kubelet. Manage docker source. the management for every node point. (Check etcd to see the statue)
    - Proxy. Networking (Load Balance)
    - Pod is basic element in node. There are one or several container in K8S.

Both docker and kubernetes provide cluster management system. 
### Difference between Docker and K8S.
- Resouce Management 
    - Docker: Service, Node, Stack, Docker
    - k8s: Pod, Service, Volume, Namespace, ReplicaSet, Deployment, StatefulSet, DaemonSet, Job
- Functinal 
    - CPU resource. k8s More accurate limits.
    - IP management. Node, Pod, Cluster IP conception. 