## Lab - Deployment

#### 1) How many PODs exist on the system?

> kubectl get pods

```
No resources found in default namespace.

Ans : 0

```
#### 2) How many ReplicaSets exist on the system?

> kubectl get replicaset

```
No resources found in default namespace.

Ans: 0

```

#### 3) How many Deployments exist on the system?

> kubectl get deployments

```
No resources found in default namespace.

Ans: 0

```

#### 4) How many Deployments exist on the system now? We just created a Deployment! Check again!

> kubectl get deployments

```
NAME                  READY   UP-TO-DATE   AVAILABLE   AGE
frontend-deployment   0/4     4            0           6s

Ans : 1

```

#### 5) How many ReplicaSets exist on the system now?

> kubectl get replicaset

```
NAME                             DESIRED   CURRENT   READY   AGE
frontend-deployment-7b9984b987   4         4         0       97s

Ans: 1

```

#### 6) How many PODs exist on the system now?

> kubectl get pods

```
NAME                                   READY   STATUS             RESTARTS   AGE
frontend-deployment-7b9984b987-p2zfd   0/1     ImagePullBackOff   0          2m23s
frontend-deployment-7b9984b987-vbtww   0/1     ImagePullBackOff   0          2m23s
frontend-deployment-7b9984b987-j78zt   0/1     ImagePullBackOff   0          2m23s
frontend-deployment-7b9984b987-4z4lm   0/1     ImagePullBackOff   0          2m23s

Ans: 4

```

#### 7) What is the image used to create the pods in the new deployment?

> kubectl describe deployments
```
Name:                   frontend-deployment
Namespace:              default
CreationTimestamp:      Wed, 15 May 2024 09:15:31 +0000
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               name=busybox-pod
Replicas:               4 desired | 4 updated | 4 total | 0 available | 4 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=busybox-pod
  Containers:
   busybox-container:
**  Image:      busybox888 **
    Port:       <none>
    Host Port:  <none>
    Command:
      sh
      -c
      echo Hello Kubernetes! && sleep 3600
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      False   MinimumReplicasUnavailable
  Progressing    True    ReplicaSetUpdated
OldReplicaSets:  <none>
NewReplicaSet:   frontend-deployment-7b9984b987 (4/4 replicas created)
Events:
  Type    Reason             Age    From                   Message
  ----    ------             ----   ----                   -------
  Normal  ScalingReplicaSet  3m45s  deployment-controller  Scaled up replica set frontend-deployment-7b9984b987 to 4

Ans: BusyBox888

```
#### 8) Create a new Deployment using the deployment-definition-1.yaml file located at /root/.There is an issue with the file, so try to fix it.
 
> kubectl explain deployment | head -n1

``` GROUP:      apps ```

* after changes

> kubectl create -f deployment-definition-1.yaml 

``` deployment.apps/deployment-1 created ```

#### 9) Create a new Deployment with the below attributes using your own deployment definition file.


* Name: httpd-frontend;
* Replicas: 3;
* Image: httpd:2.4-alpine

* first we create a yml file and then 

> kubectl create -f deployment-definition-httpd.yaml 

``` deployment.apps/httpd-frontend created ```
