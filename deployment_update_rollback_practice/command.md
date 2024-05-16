## practice

> kubectl create -f deployment_prac.yml 

``` deployment.apps/myapp-deployment created ```

> kubectl get pods

```
NAME                               READY   STATUS              RESTARTS   AGE

myapp-deployment-8874cd976-g9qj6   0/1     ErrImagePull        0          29s
myapp-deployment-8874cd976-j5wtk   0/1     ContainerCreating   0          29s
myapp-deployment-8874cd976-lcdxj   0/1     ContainerCreating   0          29s
myapp-deployment-8874cd976-smf5p   0/1     ContainerCreating   0          29s
myapp-deployment-8874cd976-w8pd9   0/1     ContainerCreating   0          29s
myapp-deployment-8874cd976-zbsxs   0/1     ContainerCreating   0          29s

```
> kubectl get replicaset

```
NAME                         DESIRED   CURRENT   READY   AGE
myapp-deployment-8874cd976   6         6         0       67s

```
> kubectl get deployment

```
NAME               READY   UP-TO-DATE   AVAILABLE   AGE
myapp-deployment   0/6     6            0           96s

```
> kubectl rollout history deployment.apps/myapp-deployment 

```
REVISION  CHANGE-CAUSE
1         <none>

```
> kubectl describe deployment myapp-deployment

```
Name:                   myapp-deployment
Namespace:              default
CreationTimestamp:      Wed, 15 May 2024 18:19:44 +0530
Labels:                 app=myapp
                        tier=frontend
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=myapp
Replicas:               3 desired | 3 updated | 3 total | 0 available | 3 unavailable
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
  Available      False   MinimumReplicasUnavailable
  Progressing    True    ReplicaSetUpdated
OldReplicaSets:  <none>
NewReplicaSet:   myapp-deployment-8874cd976 (3/3 replicas created)
Events:
  Type    Reason             Age    From                   Message
  ----    ------             ----   ----                   -------
  Normal  ScalingReplicaSet  2m46s  deployment-controller  Scaled up replica set myapp-deployment-8874cd976 to 3

```
> kubectl edit deployment myapp-deployment --record

```
Flag --record has been deprecated, --record will be removed in the future
deployment.apps/myapp-deployment edited

```
> kubectl rollout status deployment.apps/myapp-deployment 
```
Waiting for deployment "myapp-deployment" rollout to finish: 1 out of 3 new replicas have been updated...

```
> kubectl rollout status deployment.apps/myapp-deployment 

```
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 1 old replicas are pending termination...
Waiting for deployment "myapp-deployment" rollout to finish: 1 old replicas are pending termination...
deployment "myapp-deployment" successfully rolled out

```
> kubectl set image deployment myapp-deployment nginx=nginx:1.18-perl --record

```
Flag --record has been deprecated, --record will be removed in the future
deployment.apps/myapp-deployment image updated

```

> kubectl rollout status deployment/myapp-deployment

```
Waiting for deployment "myapp-deployment" rollout to finish: 1 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 1 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 1 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 2 out of 3 new replicas have been updated...
Waiting for deployment "myapp-deployment" rollout to finish: 1 old replicas are pending termination...
Waiting for deployment "myapp-deployment" rollout to finish: 1 old replicas are pending termination...
deployment "myapp-deployment" successfully rolled out

```

> kubectl rollout history deployment/myapp-deployment

```
deployment.apps/myapp-deployment 
REVISION  CHANGE-CAUSE
1         <none>
2         kubectl edit deployment myapp-deployment --record=true
3         kubectl set image deployment myapp-deployment nginx=nginx:1.18-perl --record=true

```
> kubectl get pods

```
NAME                                READY   STATUS    RESTARTS   AGE
myapp-deployment-5f9c9d5bd6-cclgw   1/1     Running   0          106s
myapp-deployment-5f9c9d5bd6-rbmb5   1/1     Running   0          3m48s
myapp-deployment-5f9c9d5bd6-rp67k   1/1     Running   0          110s

```


>  kubectl rollout undo deployment/myapp-deployment 

```
deployment.apps/myapp-deployment rolled back

```
> kubectl rollout status deployment/myapp-deployment

``` deployment "myapp-deployment" successfully rolled out ```

