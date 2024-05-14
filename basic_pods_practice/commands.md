#### 1) kubectl run nginx --image=nginx ==> We will run the command cube model run nginx, which is the name of the pod dash dash image equals to nginx. Now here is where we specify the Docker image to be used.

```
output:

pod/nginx created

(here pod by nginx is created)

```


#### 2) kubectl get pods ==> will show you the status of pods running in kubernetes

```
output:

NAME    READY   STATUS             RESTARTS   AGE

nginx   0/1     ImagePullBackOff   0          95s


```

#### 3) kubectl describe pod [pod_name] ==> will give detailed information about perticluar pod running in kube

> kubectl describe pod nginx

```
Name:             nginx
Namespace:        default
Priority:         0
Service Account:  default
Node:             minikube/192.168.49.2
Start Time:       Tue, 14 May 2024 11:12:59 +0530
Labels:           run=nginx
Annotations:      <none>
Status:           Pending
IP:               10.244.0.6
IPs:
  IP:  10.244.0.6
Containers:
  nginx:
    Container ID:   
    Image:          nginx
    Image ID:       
    Port:           <none>
    Host Port:      <none>
    State:          Waiting
      Reason:       ImagePullBackOff
    Ready:          False
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-5fz9w (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       False 
  ContainersReady             False 
  PodScheduled                True 
Volumes:
  kube-api-access-5fz9w:
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
  Type     Reason     Age                    From               Message
  ----     ------     ----                   ----               -------
  Normal   Scheduled  4m40s                  default-scheduler  Successfully assigned default/nginx to minikube
  Normal   Pulling    2m30s (x4 over 4m40s)  kubelet            Pulling image "nginx"
  Warning  Failed     2m14s (x4 over 4m24s)  kubelet            Failed to pull image "nginx": Error response from daemon: Get "https://registry-1.docker.io/v2/": dial tcp: lookup registry-1.docker.io on 192.168.49.1:53: server misbehaving
  Warning  Failed     2m14s (x4 over 4m24s)  kubelet            Error: ErrImagePull
  Warning  Failed     107s (x6 over 4m24s)   kubelet            Error: ImagePullBackOff
  Normal   BackOff    94s (x7 over 4m24s)    kubelet            Back-off pulling image "nginx"
 
```

#### 4) kubectl get pods -o wide ==> it also shows the status of pods but with the addition information

```
NAME    READY   STATUS             RESTARTS   AGE     IP           NODE       NOMINATED NODE   READINESS GATES

nginx   0/1     ImagePullBackOff   0          7m37s   10.244.0.6   minikube   <none>           <none>

```
