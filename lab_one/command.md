#### 1) How many pods exist on the system?

> kubectl get pods

```
No resources found in default namespace.

ANS: 0

```

#### 2) Create a new pod with the nginx image.

> kubectl run nginx --image=nginx

```
output:

pod/nginx created
```

#### 3) How many pods are created now?

> kubectl get pods 

```
output:

NAME            READY   STATUS    RESTARTS   AGE

nginx           1/1     Running   0          59s
newpods-kq4kw   1/1     Running   0          31s
newpods-6dl59   1/1     Running   0          31s
newpods-5f4rh   1/1     Running   0          31s

ANS: 4
```
#### 4) What is the image used to create the new pods?

> kubectl describe pods newpods-kq4kw

```
Name:             newpods-kq4kw
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.18.246.9
Start Time:       Tue, 14 May 2024 09:58:46 +0000
Labels:           tier=busybox
Annotations:      <none>
Status:           Running
IP:               10.42.0.12
IPs:
  IP:           10.42.0.12
Controlled By:  ReplicaSet/newpods
Containers:
  busybox:
    Container ID:  containerd://e3dd155dc006caab6d68a78ab04ce67592e70b654f0aad140c8c7d811ff8fec9
    Image:         busybox
    Image ID:      docker.io/library/busybox@sha256:5eef5ed34e1e1ff0a4ae850395cbf665c4de6b4b83a32a0bc7bcb998e24e7bbb
    Port:          <none>
    Host Port:     <none>
    Command:
      sleep
      1000
    State:          Running
      Started:      Tue, 14 May 2024 09:58:49 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-p6ff8 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-p6ff8:
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
  Normal  Scheduled  7m44s  default-scheduler  Successfully assigned default/newpods-kq4kw to controlplane
  Normal  Pulling    7m42s  kubelet            Pulling image "busybox"
  Normal  Pulled     7m42s  kubelet            Successfully pulled image "busybox" in 394ms (394ms including waiting)
  Normal  Created    7m42s  kubelet            Created container busybox
  Normal  Started    7m41s  kubelet            Started container busybox

```

> kubectl describe pods newpods-6dl59 

```
Name:             newpods-6dl59
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.18.246.9
Start Time:       Tue, 14 May 2024 09:58:46 +0000
Labels:           tier=busybox
Annotations:      <none>
Status:           Running
IP:               10.42.0.10
IPs:
  IP:           10.42.0.10
Controlled By:  ReplicaSet/newpods
Containers:
  busybox:
    Container ID:  containerd://8497f0f42dcc5fee32b30a4b0345dac254f04639d2b930bec8476f9394adc34d
    Image:         busybox
    Image ID:      docker.io/library/busybox@sha256:5eef5ed34e1e1ff0a4ae850395cbf665c4de6b4b83a32a0bc7bcb998e24e7bbb
    Port:          <none>
    Host Port:     <none>
    Command:
      sleep
      1000
    State:          Running
      Started:      Tue, 14 May 2024 09:58:49 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-xqx2f (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-xqx2f:
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
  Normal  Scheduled  8m35s  default-scheduler  Successfully assigned default/newpods-6dl59 to controlplane
  Normal  Pulling    8m34s  kubelet            Pulling image "busybox"
  Normal  Pulled     8m33s  kubelet            Successfully pulled image "busybox" in 601ms (601ms including waiting)
  Normal  Created    8m33s  kubelet            Created container busybox
  Normal  Started    8m32s  kubelet            Started container busybox

```

``` ANS: BusyBox ```



#### 5)


> kubectl describe pod newpods-kq4kw

```
Name:             newpods-kq4kw
Namespace:        default
Priority:         0
Service Account:  default
** Node:          controlplane/192.18.246.9 **
Start Time:       Tue, 14 May 2024 09:58:46 +0000
Labels:           tier=busybox
Annotations:      <none>
Status:           Running
IP:               10.42.0.12
IPs:
  IP:           10.42.0.12
Controlled By:  ReplicaSet/newpods
Containers:
  busybox:
    Container ID:  containerd://e3dd155dc006caab6d68a78ab04ce67592e70b654f0aad140c8c7d811ff8fec9
    Image:         busybox
    Image ID:      docker.io/library/busybox@sha256:5eef5ed34e1e1ff0a4ae850395cbf665c4de6b4b83a32a0bc7bcb998e24e7bbb
    Port:          <none>
    Host Port:     <none>
    Command:
      sleep
      1000
    State:          Running
      Started:      Tue, 14 May 2024 09:58:49 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-p6ff8 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-p6ff8:
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
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  10m   default-scheduler  Successfully assigned default/newpods-kq4kw to controlplane
  Normal  Pulling    10m   kubelet            Pulling image "busybox"
  Normal  Pulled     10m   kubelet            Successfully pulled image "busybox" in 394ms (394ms including waiting)
  Normal  Created    10m   kubelet            Created container busybox
  Normal  Started    10m   kubelet            Started container busybox


ANS : ControlPlane
```

#### 6) How many containers are part of the pod webapp?

> kubectl describe pod webapp

```
Name:             webapp
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.18.246.9
Start Time:       Tue, 14 May 2024 10:12:34 +0000
Labels:           <none>
Annotations:      <none>
Status:           Pending
IP:               10.42.0.13
IPs:
  IP:  10.42.0.13
Containers:
  nginx:
    Container ID:   containerd://7b784af5511ace47b193f1dbf081671e3c8b57d0267a7344ef1b51464821dcd4
    Image:          nginx
    Image ID:       docker.io/library/nginx@sha256:32e76d4f34f80e479964a0fbd4c5b4f6967b5322c8d004e9cf0cb81c93510766
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Tue, 14 May 2024 10:12:35 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-2sqth (ro)
  agentx:
    Container ID:   
    Image:          agentx
    Image ID:       
    Port:           <none>
    Host Port:      <none>
    State:          Waiting
      Reason:       ImagePullBackOff
    Ready:          False
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-2sqth (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       False 
  ContainersReady             False 
  PodScheduled                True 
Volumes:
  kube-api-access-2sqth:
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
  Type     Reason     Age                   From               Message
  ----     ------     ----                  ----               -------
  Normal   Scheduled  2m33s                 default-scheduler  Successfully assigned default/webapp to controlplane
  Normal   Pulling    2m33s                 kubelet            Pulling image "nginx"
  Normal   Pulled     2m33s                 kubelet            Successfully pulled image "nginx" in 170ms (170ms including waiting)
  Normal   Created    2m33s                 kubelet            Created container nginx
  Normal   Started    2m33s                 kubelet            Started container nginx
  Warning  Failed     109s (x3 over 2m32s)  kubelet            Error: ErrImagePull
  Normal   BackOff    81s (x5 over 2m32s)   kubelet            Back-off pulling image "agentx"
  Warning  Failed     81s (x5 over 2m32s)   kubelet            Error: ImagePullBackOff
  Normal   Pulling    66s (x4 over 2m33s)   kubelet            Pulling image "agentx"
  Warning  Failed     66s (x4 over 2m32s)   kubelet            Failed to pull image "agentx": failed to pull and unpack image "docker.io/library/agentx:latest": failed to resolve reference "docker.io/library/agentx:latest": pull access denied, repository does not exist or may require authorization: server message: insufficient_scope: authorization failed

ANS : 2

```
#### 7) What images are used in the new webapp pod?

> kubectl describe pod webapp

```

Name:             webapp
Namespace:        default
Priority:         0
Service Account:  default
Node:             controlplane/192.18.246.9
Start Time:       Tue, 14 May 2024 10:12:34 +0000
Labels:           <none>
Annotations:      <none>
Status:           Pending
IP:               10.42.0.13
IPs:
  IP:  10.42.0.13
Containers:
  nginx:
    Container ID:   containerd://7b784af5511ace47b193f1dbf081671e3c8b57d0267a7344ef1b51464821dcd4
    Image:          nginx
    Image ID:       docker.io/library/nginx@sha256:32e76d4f34f80e479964a0fbd4c5b4f6967b5322c8d004e9cf0cb81c93510766
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Tue, 14 May 2024 10:12:35 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-2sqth (ro)
  agentx:
    Container ID:   
    Image:          agentx
    Image ID:       
    Port:           <none>
    Host Port:      <none>
    State:          Waiting
      Reason:       ImagePullBackOff
    Ready:          False
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-2sqth (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       False 
  ContainersReady             False 
  PodScheduled                True 
Volumes:
  kube-api-access-2sqth:
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
  Type     Reason     Age                   From               Message
  ----     ------     ----                  ----               -------
  Normal   Scheduled  2m33s                 default-scheduler  Successfully assigned default/webapp to controlplane
  Normal   Pulling    2m33s                 kubelet            Pulling image "nginx"
  Normal   Pulled     2m33s                 kubelet            Successfully pulled image "nginx" in 170ms (170ms including waiting)
  Normal   Created    2m33s                 kubelet            Created container nginx
  Normal   Started    2m33s                 kubelet            Started container nginx
  Warning  Failed     109s (x3 over 2m32s)  kubelet            Error: ErrImagePull
  Normal   BackOff    81s (x5 over 2m32s)   kubelet            Back-off pulling image "agentx"
  Warning  Failed     81s (x5 over 2m32s)   kubelet            Error: ImagePullBackOff
  Normal   Pulling    66s (x4 over 2m33s)   kubelet            Pulling image "agentx"
  Warning  Failed     66s (x4 over 2m32s)   kubelet            Failed to pull image "agentx": failed to pull and unpack image "docker.io/library/agentx:latest": failed to resolve reference "docker.io/library/agentx:latest": pull access denied, repository does not exist or may require authorization: server message: insufficient_scope: authorization failed

ANS: nginx & agentx

``` 
#### 8) Delete the webapp Pod.

>  kubectl delete pod webapp

``` pod "webapp" deleted ```


#### 9) Create a new pod with the name redis and the image redis123.

> kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml

> kubectl create -f redis-definition.yaml
``` pod/redis created ```

> kubectl get pods

```
NAME            READY   STATUS         RESTARTS        AGE

nginx           1/1     Running        0               24m
newpods-kq4kw   1/1     Running        1 (7m44s ago)   24m
newpods-6dl59   1/1     Running        1 (7m44s ago)   24m
newpods-5f4rh   1/1     Running        1 (7m44s ago)   24m
redis           0/1     ErrImagePull   0               5s

```

#### 10) Now change the image on this pod to redis.Once done, the pod should be in a running state.

> kubectl edit pod redis : this will let you change in running pod

> kubectl apply -f redis-defination.yml : this is changed yml file which will run to make change in currently running pod once we edit the file

```
Warning: resource pods/redis is missing the kubectl.kubernetes.io/last-applied-configuration annotation which is required by kubectl apply. kubectl apply should only be used on resources created declaratively by either kubectl create --save-config or kubectl apply. The missing annotation will be patched automatically.
pod/redis configured

```

