# ON CDEC B13

## Kubernetes
-------------

Orchestration Tools - Management Tools 

Architecture 

CLuster - Master Slave

Master Node (Control Plane)   - Slave (Worker Node)
Multiple (high Availability)            - Multiple / advantages?
                                        - Fault tolerance, Backup, LowLatency, (Balancing Load)


Control Plane 
API Server - 
ETCD - 
Scheduler - 
Controller Manager - 

  - Worker Node
  Kubelet
  Kubeproxy

-------------------------------
Lifecycle of POD
---------------
Command -> API Server -> ETCD -> API Server -> Scheduler -> API Server -> Kubelet -> API Server -> ETCD
---------------

## How to create cluster?
minikube - HW
kind - HW
EKS - Cluster
GKE
AKS
DOKS
Kubeadm
KillerKoda - k8s lab

--------------

Kubernetes Objects
------------------
Pod - Enwrapment Around Container. Smallest deployable entity in Kubernetes.
Service - Expose application outside the cluster
    - Headless
    - ClusterIP - Expose app inside the cluster
    - NodePort - Expose app outside the cluster on endpoint as NODEIP:NODEPORT
    - LoadBalancer - Expose app outside the cluster on Cloud LoadBalancer
namespace - Folders / Devide your clusters / segregate k8s objects
replication Controller - to manage replicas of the pods. Equality Based Selector 
Replica Set - to manage replicas of the pods. Set based Selector.
Deployments - to manage deployment of replicas of the pods. 
Daemon Set - to create pod in every node 
Stateful Set - to manage replicas of the stateful pods
ConfigMap and  Secrets- Store Varaibles and Secret Variables
PV and PVC - Persistent volume and Persistent Volume
Ingress - Networking, routing. Path based routing and Name based routing
HPA - Horizontal Pod Autoscaler

## Revision

Architecture Kubernetes
Lifecycle of POD
POD
Services


YAML -> Manifest



Replication Controller: Manage Replicas of pod

```shell
kubectl api-resources     # info about objects
kubectl api-versions      # info about API versions
kubectl create ns <NAME>  # create new namespace
kubectl scale rc --replicas 2 <RC_NAME>   # scale up/down the replicas of pod of replicationcontroller
kubectl edit rc <RC_NAME>   # edit existing k8s object rc
```

RC | RS

v1 |  app/v1
Previous G | Advance G
selector
  app: my-app

set based selector-
set of matching labels

set based Operators
  
In, NotIn, Exist

 - { key: env, operator: In , values: [releas,dev] }


 SET { apple, banana, mango, orange }
 list [ apple, banana, mango, apple, mango, orange, orange ] 

 100 pods

 app: cbz
 app: dyl
 app: greamio
 env: prod
 env: dev
 env: release
 env: dev

### Deployments
- Replicas - ReplicaSet
- Startegy 

### StatefulSet
- Replicas stateful applications


stateless application   |    Stateful Application   
HTTPD, Nginx, Frontend  |  Database server, Rabitmq, MongoDB
--------------------
Deployment              | Stateful application
Randomly pod created    | Seq poc created
Randomly pod deleted    | Seq pod deleted
Random hashes in name   | Seq char in name
All pods read/write     | Master pod can read/write, other pods read only
All pods created from image   |  only first pod created from image, remaining will be created sequestially from previous pod


### Daemon Set
- Makesure to deploy a pod on every node
- filter node on the basis labels

1 - env: dev - 1
2 - env: prod
3 - env: dev - 1
4 - env: dev - 1
5 - env: prod



deployment = 4 | nodeSelector - env: dev |
daemonSet | nodeSelector - env: dev



### ConfigMaps
- Variables
key: values

Deploy a java application on kubernetes cluster
- Deployment
- Service

### HPA - Horizontal Pod Autoscaler

Horizontal Autoscaling and Vertical Autoscaling

1) Virtical Scaling
2) HPA
3) Node Autoscaling

Instance CPU-RAM-Storage

Pod-Container -> Host machine (CPU, MEM)

Application(LOOP)- pod- host (CPU, MEM)

Request and Limit
Request:
  cpu: 1 Core
  mem: 50 MB

limit:
  cpu: 2 Core
  mem: 500 MB

HPA, HorizontalpodAutoscaler
Number pod (CPU-UTILIZATION) - metrics
Metrics Server - 

Node Auto Scaling - NodeGroup desried = 2, min = 1, max = 5

Loadbalancer


 Ingres

What - 
Why - 
How - 

Theory | 

DevOps engineer


Project - 
-----------


Applications three tier - 

amazon.jar - 

database - application (java) 

Frontend (HTML)
Backend (Java)
Database (Mariadb)

TechStack:

Frontend - index.html
Backend - Maven / JAva Application
Database - Mariadb
----------












































