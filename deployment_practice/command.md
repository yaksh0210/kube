## Practice commands


> kubectl create -f deployment.yml 

``` deployment.apps/myapp-deployment created ```

> kubectl get all

```
NAME                                   READY   STATUS    RESTARTS   AGE

pod/myapp-deployment-8874cd976-5k5nn   1/1     Running   0          12s
pod/myapp-deployment-8874cd976-988mt   1/1     Running   0          12s
pod/myapp-deployment-8874cd976-g8jql   1/1     Running   0          12s

NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/hello-minikube   NodePort    10.96.233.212   <none>        8080:32558/TCP   27h
service/kubernetes       ClusterIP   10.96.0.1       <none>        443/TCP          2d1h

NAME                               READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/myapp-deployment   3/3     3            3           12s

NAME                                         DESIRED   CURRENT   READY   AGE
replicaset.apps/myapp-deployment-8874cd976   3         3         3       12s

```

> kubectl describe deployment myapp-deployment

```
Name:                   myapp-deployment
Namespace:              default
CreationTimestamp:      Wed, 15 May 2024 14:25:18 +0530
Labels:                 app=nginx
                        tier=frontend
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=myapp
Replicas:               3 desired | 3 updated | 3 total | 3 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=myapp
  Containers:
   nginx:
    Image:         nginx
    Port:          <none>
    Host Port:     <none>
    Environment:   <none>
    Mounts:        <none>
  Volumes:         <none>
  Node-Selectors:  <none>
  Tolerations:     <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   myapp-deployment-8874cd976 (3/3 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  116s  deployment-controller  Scaled up replica set myapp-deployment-8874cd976 to 3

```


