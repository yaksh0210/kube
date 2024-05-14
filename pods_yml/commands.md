----------------------------------------------------------------------------

* first we will create an yml file which is attached below this file 

##### 1) kubectl apply/create -f pods.yml ==> it is the first command to create a pod where  apply and create anything you can use and also -f is stands for file and pods.yml is our file which i have created

> kubectl apply -f pods.yml

``` pod/nginx unchanged ```

* as i have already run it once it shows unchanged state if it is the first time then it will show created.



#### 2) now i will see my pods running using

> kubectl get pods
```
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          178m

```

#### 3) if i want in detailed description regarding my pods then

> kubectl describe pods 

```
Name:             nginx
Namespace:        default
Priority:         0
Service Account:  default
Node:             minikube/192.168.49.2
Start Time:       Tue, 14 May 2024 11:12:59 +0530
Labels:           app=nginx
                  run=nginx
                  tier=frontend
Annotations:      <none>
Status:           Running
IP:               10.244.0.6
IPs:
  IP:  10.244.0.6
Containers:
  nginx:
    Container ID:   docker://f1bf35a0521bc0e4bb6f4567930c11a89e8eda26a6a860780a80977842dd26e7
    Image:          nginx
    Image ID:       docker-pullable://nginx@sha256:32e76d4f34f80e479964a0fbd4c5b4f6967b5322c8d004e9cf0cb81c93510766
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Tue, 14 May 2024 14:09:43 +0530
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-5fz9w (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
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
  Type     Reason   Age                    From     Message
  ----     ------   ----                   ----     -------
  Normal   BackOff  68m (x454 over 178m)   kubelet  Back-off pulling image "nginx"
  Warning  Failed   63m (x26 over 178m)    kubelet  Failed to pull image "nginx": Error response from daemon: Get "https://registry-1.docker.io/v2/": dial tcp: lookup registry-1.docker.io on 192.168.49.1:53: server misbehaving
  Normal   Pulling  6m28s (x27 over 178m)  kubelet  Pulling image "nginx"

```




----------------------------------------------------------------------------
