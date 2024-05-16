## LAB - deployment update and rollout

#### 1) Inspect the deployment and identify the number of PODs deployed by it

>  kubectl describe pods
```
Name:             frontend-685dfcc44-29m7j
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.8.142.6
Start Time:       Thu, 16 May 2024 05:35:51 +0000
Labels:           name=webapp
                  pod-template-hash=685dfcc44
Annotations:      <none>
Status:           Running
IP:               10.42.0.10
IPs:
  IP:           10.42.0.10
Controlled By:  ReplicaSet/frontend-685dfcc44
Containers:
  simple-webapp:
    Container ID:   containerd://5a20ceac37d8b9639383ae647962963f1eaf26796f8fcaa5ee4fc50d514e1c1d
    Image:          kodekloud/webapp-color:v1
    Image ID:       docker.io/kodekloud/webapp-color@sha256:27b1e0cbd55a646824c231c896bf77f8278f2d335c4f2b47cbb258edf8281ceb
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 16 May 2024 05:35:59 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-xtqlc (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-xtqlc:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age    From               Message
  ----    ------     ----   ----               -------
  Normal  Scheduled  6m35s  default-scheduler  Successfully assigned default/frontend-685dfcc44-29m7j to controlplane
  Normal  Pulling    6m34s  kubelet            Pulling image "kodekloud/webapp-color:v1"
  Normal  Pulled     6m29s  kubelet            Successfully pulled image "kodekloud/webapp-color:v1" in 4.884s (4.884s including waiting)
  Normal  Created    6m29s  kubelet            Created container simple-webapp
  Normal  Started    6m28s  kubelet            Started container simple-webapp


Name:             frontend-685dfcc44-vjt58
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.8.142.6
Start Time:       Thu, 16 May 2024 05:35:51 +0000
Labels:           name=webapp
                  pod-template-hash=685dfcc44
Annotations:      <none>
Status:           Running
IP:               10.42.0.11
IPs:
  IP:           10.42.0.11
Controlled By:  ReplicaSet/frontend-685dfcc44
Containers:
  simple-webapp:
    Container ID:   containerd://fd307a94918ba0d38045a4f1a70727f9e053a52056b43060c24a2215f2b7e9a3
    Image:          kodekloud/webapp-color:v1
    Image ID:       docker.io/kodekloud/webapp-color@sha256:27b1e0cbd55a646824c231c896bf77f8278f2d335c4f2b47cbb258edf8281ceb
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 16 May 2024 05:35:59 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-p52vm (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-p52vm:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age    From               Message
  ----    ------     ----   ----               -------
  Normal  Scheduled  6m35s  default-scheduler  Successfully assigned default/frontend-685dfcc44-vjt58 to controlplane
  Normal  Pulling    6m34s  kubelet            Pulling image "kodekloud/webapp-color:v1"
  Normal  Pulled     6m29s  kubelet            Successfully pulled image "kodekloud/webapp-color:v1" in 4.674s (4.674s including waiting)
  Normal  Created    6m29s  kubelet            Created container simple-webapp
  Normal  Started    6m28s  kubelet            Started container simple-webapp


Name:             frontend-685dfcc44-zfpq4
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.8.142.6
Start Time:       Thu, 16 May 2024 05:35:51 +0000
Labels:           name=webapp
                  pod-template-hash=685dfcc44
Annotations:      <none>
Status:           Running
IP:               10.42.0.13
IPs:
  IP:           10.42.0.13
Controlled By:  ReplicaSet/frontend-685dfcc44
Containers:
  simple-webapp:
    Container ID:   containerd://146be3044a9287ebd2715e035f07e74ca4d36bd8b320ef7cae5cfbc8c65f8dca
    Image:          kodekloud/webapp-color:v1
    Image ID:       docker.io/kodekloud/webapp-color@sha256:27b1e0cbd55a646824c231c896bf77f8278f2d335c4f2b47cbb258edf8281ceb
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 16 May 2024 05:35:59 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-hddf2 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-hddf2:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age    From               Message
  ----    ------     ----   ----               -------
  Normal  Scheduled  6m35s  default-scheduler  Successfully assigned default/frontend-685dfcc44-zfpq4 to controlplane
  Normal  Pulling    6m34s  kubelet            Pulling image "kodekloud/webapp-color:v1"
  Normal  Pulled     6m29s  kubelet            Successfully pulled image "kodekloud/webapp-color:v1" in 4.566s (4.566s including waiting)
  Normal  Created    6m29s  kubelet            Created container simple-webapp
  Normal  Started    6m28s  kubelet            Started container simple-webapp


Name:             frontend-685dfcc44-m42lv
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.8.142.6
Start Time:       Thu, 16 May 2024 05:35:51 +0000
Labels:           name=webapp
                  pod-template-hash=685dfcc44
Annotations:      <none>
Status:           Running
IP:               10.42.0.12
IPs:
  IP:           10.42.0.12
Controlled By:  ReplicaSet/frontend-685dfcc44
Containers:
  simple-webapp:
    Container ID:   containerd://e1a02ae9ff490f367bbdc072454568c71e3306567f4b14f12d7a1903918ffa95
    Image:          kodekloud/webapp-color:v1
    Image ID:       docker.io/kodekloud/webapp-color@sha256:27b1e0cbd55a646824c231c896bf77f8278f2d335c4f2b47cbb258edf8281ceb
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Thu, 16 May 2024 05:35:59 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-k6lm9 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-k6lm9:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age    From               Message
  ----    ------     ----   ----               -------
  Normal  Scheduled  6m35s  default-scheduler  Successfully assigned default/frontend-685dfcc44-m42lv to controlplane
  Normal  Pulling    6m34s  kubelet            Pulling image "kodekloud/webapp-color:v1"
  Normal  Pulled     6m29s  kubelet            Successfully pulled image "kodekloud/webapp-color:v1" in 4.765s (4.765s including waiting)
  Normal  Created    6m29s  kubelet            Created container simple-webapp
  Normal  Started    6m28s  kubelet            Started container simple-webapp


ANS: 4

```
#### 2) What container image is used to deploy the applications?

> kubectl describe deployment

```
Name:                   frontend
Namespace:              default
CreationTimestamp:      Thu, 16 May 2024 05:35:51 +0000
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               name=webapp
Replicas:               4 desired | 4 updated | 4 total | 4 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        20
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=webapp
  Containers:
   simple-webapp:
*   Image:        kodekloud/webapp-color:v1
    Port:         8080/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   frontend-685dfcc44 (4/4 replicas created)
Events:
  Type    Reason             Age    From                   Message
  ----    ------             ----   ----                   -------
  Normal  ScalingReplicaSet  8m33s  deployment-controller  Scaled up replica set frontend-685dfcc44 to 4

```


#### 3) Let us try that. Upgrade the application by setting the image on the deployment to kodekloud/webapp-color:v2 .Do not delete and re-create the deployment. Only set the new image name for the existing deployment.


> kubectl edit deployment frontend 

```
# Please edit the object below. Lines beginning with a '#' will be ignored,
# and an empty file will abort the edit. If an error occurs while saving this file will be
# reopened with the relevant failures.
#
apiVersion: apps/v1
kind: Deployment
metadata:
  annotations:
    deployment.kubernetes.io/revision: "1"
  creationTimestamp: "2024-05-16T05:35:51Z"
  generation: 1
  name: frontend
  namespace: default
  resourceVersion: "1028"
  uid: 550622bf-1173-42f6-8e5c-a173cba5598d
spec:
  minReadySeconds: 20
  progressDeadlineSeconds: 600
  replicas: 4
  revisionHistoryLimit: 10
  selector:
    matchLabels:
      name: webapp
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
  template:
    metadata:
      creationTimestamp: null
      labels:
        name: webapp
    spec:
      containers:
      - image: kodekloud/webapp-color:v3
        imagePullPolicy: IfNotPresent
        name: simple-webapp
        ports:
        - containerPort: 8080
          protocol: TCP
        resources: {}
        terminationMessagePath: /dev/termination-log
        terminationMessagePolicy: File
      dnsPolicy: ClusterFirst

restartPolicy: Always
      schedulerName: default-scheduler
      securityContext: {}
      terminationGracePeriodSeconds: 30
status:
  availableReplicas: 4
  conditions:
  - lastTransitionTime: "2024-05-16T05:36:20Z"
    lastUpdateTime: "2024-05-16T05:36:20Z"
    message: Deployment has minimum availability.
    reason: MinimumReplicasAvailable
    status: "True"
    type: Available
  - lastTransitionTime: "2024-05-16T05:35:51Z"
    lastUpdateTime: "2024-05-16T05:36:20Z"
    message: ReplicaSet "frontend-685dfcc44" has successfully progressed.
    reason: NewReplicaSetAvailable
    status: "True"
    type: Progressing
  observedGeneration: 1
  readyReplicas: 4
  replicas: 4
  updatedReplicas: 4

```

``` deployment.apps/frontend edited ```



#### 4) Up to how many PODs can be down for upgrade at a time.Consider the current strategy settings and number of PODs - 4


> kubectl describe deployment frontend

```
Name:                   frontend
Namespace:              default
CreationTimestamp:      Thu, 16 May 2024 05:35:51 +0000
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 3
Selector:               name=webapp
Replicas:               4 desired | 4 updated | 4 total | 4 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        20
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=webapp
  Containers:
   simple-webapp:
    Image:        kodekloud/webapp-color:v2
    Port:         8080/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  frontend-685dfcc44 (0/0 replicas created), frontend-7d9ccf9966 (0/0 replicas created)
NewReplicaSet:   frontend-dbb8f4b47 (4/4 replicas created)
Events:
  Type    Reason             Age                From                   Message
  ----    ------             ----               ----                   -------
  Normal  ScalingReplicaSet  16m                deployment-controller  Scaled up replica set frontend-685dfcc44 to 4
  Normal  ScalingReplicaSet  2m55s              deployment-controller  Scaled up replica set frontend-7d9ccf9966 to 1
  Normal  ScalingReplicaSet  2m55s              deployment-controller  Scaled down replica set frontend-685dfcc44 to 3 from 4
  Normal  ScalingReplicaSet  2m55s              deployment-controller  Scaled up replica set frontend-7d9ccf9966 to 2 from 1
  Normal  ScalingReplicaSet  2m31s              deployment-controller  Scaled down replica set frontend-685dfcc44 to 1 from 3
  Normal  ScalingReplicaSet  2m31s              deployment-controller  Scaled up replica set frontend-7d9ccf9966 to 4 from 2
  Normal  ScalingReplicaSet  2m8s               deployment-controller  Scaled down replica set frontend-685dfcc44 to 0 from 1
  Normal  ScalingReplicaSet  108s               deployment-controller  Scaled up replica set frontend-dbb8f4b47 to 1
  Normal  ScalingReplicaSet  108s               deployment-controller  Scaled down replica set frontend-7d9ccf9966 to 3 from 4
  Normal  ScalingReplicaSet  108s               deployment-controller  Scaled up replica set frontend-dbb8f4b47 to 2 from 1
  Normal  ScalingReplicaSet  63s (x3 over 85s)  deployment-controller  (combined from similar events): Scaled down replica set frontend-7d9ccf9966 to 0 from 1

ANS: 1
```
