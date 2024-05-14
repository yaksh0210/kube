### Perfomred commands

> kubectl create -f replicaset.yml 

``` replicaset.apps/myapp-replicaset created ```

> kubectl get replicaset

```
NAME               DESIRED   CURRENT   READY   AGE

myapp-replicaset   3         3         3       88s

```

> kubectl get pods

```
NAME                     READY   STATUS    RESTARTS   AGE

myapp-replicaset-6w6p6   1/1     Running   0          2m16s
myapp-replicaset-gf9ll   1/1     Running   0          2m16s
myapp-replicaset-xn5bf   1/1     Running   0          2m16s

```


> kubectl delete pod myapp-replicaset-6w6p6

``` pod "myapp-replicaset-6w6p6" deleted ```

> kubectl get pods

```
NAME                     READY   STATUS    RESTARTS   AGE

myapp-replicaset-gf9ll   1/1     Running   0          4m3s
**myapp-replicaset-r8gnt   1/1     Running   0          17s**
myapp-replicaset-xn5bf   1/1     Running   0          4m3s

```

> kubectl describe replicaset myapp-replicaset

```
Name:         myapp-replicaset
Namespace:    default
Selector:     app=myapp
Labels:       app=myapp
Annotations:  <none>
Replicas:     3 current / 3 desired
Pods Status:  3 Running / 0 Waiting / 0 Succeeded / 0 Failed
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
Events:
  Type    Reason            Age   From                   Message
  ----    ------            ----  ----                   -------
  Normal  SuccessfulCreate  13m   replicaset-controller  Created pod: myapp-replicaset-6w6p6
  Normal  SuccessfulCreate  13m   replicaset-controller  Created pod: myapp-replicaset-xn5bf
  Normal  SuccessfulCreate  13m   replicaset-controller  Created pod: myapp-replicaset-gf9ll
  Normal  SuccessfulCreate  10m   replicaset-controller  Created pod: myapp-replicaset-r8gnt

```

> kubectl edit replicaset myapp-replicaset

``` replicaset.apps/myapp-replicaset edited ```

> kubectl get replicaset

```
NAME               DESIRED   CURRENT   READY   AGE

myapp-replicaset   4         4         4       20m

```

> kubectl scale replicaset myapp-replicaset --replicas=2

``` replicaset.apps/myapp-replicaset scaled ```

> kubectl get pods

```
NAME                     READY   STATUS    RESTARTS   AGE

myapp-replicaset-gf9ll   1/1     Running   0          23m
myapp-replicaset-xn5bf   1/1     Running   0          23m

```
