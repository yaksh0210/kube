## LAB - Service

#### 1) How many Services exist on the system?

> kubectl get services

```
NAME         TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE

kubernetes   ClusterIP   10.43.0.1    <none>        443/TCP   19m

ANS: 1

```

#### 2) What is the type of the default kubernetes service?


> kubectl get services

```
NAME        * TYPE*      CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
kubernetes   ClusterIP   10.43.0.1    <none>        443/TCP   20m

ANS : ClusterIP
```

#### 3) What is the targetPort configured on the kubernetes service?


> kubectl describe service

```

Name:              kubernetes
Namespace:         default
Labels:            component=apiserver
                   provider=kubernetes
Annotations:       <none>
Selector:          <none>
Type:              ClusterIP
IP Family Policy:  SingleStack
IP Families:       IPv4
IP:                10.43.0.1
IPs:               10.43.0.1
Port:              https  443/TCP
TargetPort:        6443/TCP
Endpoints:         192.7.160.3:6443
Session Affinity:  None
Events:            <none>


ANS : 6443

```

#### 4)How many labels are configured on the kubernetes service?



> kubectl describe service

```
Name:              kubernetes
Namespace:         default
Labels:            component=apiserver
                   provider=kubernetes
Annotations:       <none>
Selector:          <none>
Type:              ClusterIP
IP Family Policy:  SingleStack
IP Families:       IPv4
IP:                10.43.0.1
IPs:               10.43.0.1
Port:              https  443/TCP
TargetPort:        6443/TCP
Endpoints:         192.7.160.3:6443
Session Affinity:  None
Events:            <none>


ANS : 2

```

#### 5) How many Deployments exist on the system now?

> kubectl get deployment

```
NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
simple-webapp-deployment   4/4     4            4           16s

ANS: 1
```

#### 6) What is the image used to create the pods in the deployment?


> kubectl describe deployment

```
Name:                   simple-webapp-deployment
Namespace:              default
CreationTimestamp:      Fri, 17 May 2024 05:31:01 +0000
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               name=simple-webapp
Replicas:               4 desired | 4 updated | 4 total | 4 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  name=simple-webapp
  Containers:
   simple-webapp:
    Image:        kodekloud/simple-webapp:red
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
NewReplicaSet:   simple-webapp-deployment-7b447ccc74 (4/4 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  74s   deployment-controller  Scaled up replica set simple-webapp-deployment-7b447ccc74 to 4


ANS: kodekloud/simple-webapp:red

```

#### 7) Create a new service to access the web application using the service-definition-1.yaml file.

* Name: webapp-service
* Type: NodePort
* targetPort: 8080
* port: 8080
* nodePort: 30080
* selector:
*  name: simple-webapp



> kubectl create -f service-definition-1.yaml 

``` service/webapp-service created ```

> kubectl get service

```
NAME             TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes       ClusterIP   10.43.0.1      <none>        443/TCP          30m
webapp-service   NodePort    10.43.223.20   <none>        8080:30080/TCP   2m3s
```


