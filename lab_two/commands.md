### practice 

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
#### 3) How about now? How many ReplicaSets do you see? We just made a few changes!

> kubectl get replicaset

```
NAME              DESIRED   CURRENT   READY   AGE
new-replica-set   4         4         0       9s

Ans: 1
```

#### 4) How many PODs are DESIRED in the new-replica-set?

> kubectl get replicaset

```
NAME              DESIRED   CURRENT   READY   AGE
new-replica-set   4         4         0       32s

Ans: 4

```


#### 5) What is the image used to create the pods in the new-replica-set?

> kubectl describe replicaset

```
Name:         new-replica-set
Namespace:    default
Selector:     name=busybox-pod
Labels:       <none>
Annotations:  <none>
Replicas:     4 current / 4 desired
Pods Status:  0 Running / 4 Waiting / 0 Succeeded / 0 Failed
Pod Template:
  Labels:  name=busybox-pod
  Containers:
   busybox-container:
**  Image:      busybox777 **
    Port:       <none>
    Host Port:  <none>
    Command:
      sh
      -c
      echo Hello Kubernetes! && sleep 3600
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Events:
  Type    Reason            Age    From                   Message
  ----    ------            ----   ----                   -------
  Normal  SuccessfulCreate  2m12s  replicaset-controller  Created pod: new-replica-set-dh5tc
  Normal  SuccessfulCreate  2m12s  replicaset-controller  Created pod: new-replica-set-7fv46
  Normal  SuccessfulCreate  2m12s  replicaset-controller  Created pod: new-replica-set-kpt2q
  Normal  SuccessfulCreate  2m12s  replicaset-controller  Created pod: new-replica-set-k5bkk


Ans : busybox777

```

#### 6) How many PODs are READY in the new-replica-set?

> kubectl get replicaset

```
NAME              DESIRED   CURRENT   READY   AGE
new-replica-set   4         4         0       3m39s

Ans: 0

```
#### 7) Delete any one of the 4 PODs.

> kubectl get pods

```

NAME                    READY   STATUS             RESTARTS   AGE
new-replica-set-dh5tc   0/1     ImagePullBackOff   0          5m39s
new-replica-set-7fv46   0/1     ImagePullBackOff   0          5m39s
new-replica-set-k5bkk   0/1     ImagePullBackOff   0          5m39s
new-replica-set-kpt2q   0/1     ImagePullBackOff   0          5m39s

```
> kubectl delete pod new-replica-set-dh5tc

``` pod "new-replica-set-dh5tc" deleted ```

#### 8) How many PODs exist now?

> kubectl get pods

```
NAME                    READY   STATUS             RESTARTS   AGE
new-replica-set-7fv46   0/1     ImagePullBackOff   0          7m7s
new-replica-set-k5bkk   0/1     ImagePullBackOff   0          7m7s
new-replica-set-kpt2q   0/1     ImagePullBackOff   0          7m7s
new-replica-set-c6tdc   0/1     ErrImagePull       0          59s

Ans: 4

```
#### 9) Create a ReplicaSet using the replicaset-definition-1.yaml

>  kubectl create -f replicaset-definition-1.yaml

``` replicaset.apps/replicaset-1 created ```


#### 10) Fix the issue in the replicaset-definition-2.yaml file and create a ReplicaSet using it.

> kubectl create -f replicaset-definition-2.yaml 

``` replicaset.apps/replicaset-2 created ```




#### 11) Delete the two newly created ReplicaSets - replicaset-1 and replicaset-2

> kubectl delete -f replicaset-definition-1.yaml 

``` replicaset.apps "replicaset-1" deleted ```

> kubectl delete -f replicaset-definition-2.yaml 

``` replicaset.apps "replicaset-2" deleted ```

#### 12) Fix the original replica set new-replica-set to use the correct busybox image.

> kubectl edit replicaset new-replica-set 

``` replicaset.apps/new-replica-set edited ```
>  kubectl get pods

```
NAME                    READY   STATUS             RESTARTS   AGE
new-replica-set-294ll   0/1     ImagePullBackOff   0          8m13s
new-replica-set-5hf9f   0/1     ImagePullBackOff   0          8m13s
new-replica-set-mp9tl   0/1     ImagePullBackOff   0          8m13s
new-replica-set-hrt6s   0/1     ImagePullBackOff   0          8m13s
```

> kubectl delete po new-replica-set-294ll 

```pod "new-replica-set-294ll" deleted ```

> kubectl delete po new-replica-set-5hf9f

```pod "new-replica-set-5hf9f" deleted```

> kubectl delete po new-replica-set-mp9tl

```pod "new-replica-set-mp9tl" deleted```

> kubectl delete po new-replica-set-hrt6s

```pod "new-replica-set-hrt6s" deleted```

#### 13) Scale the ReplicaSet to 5 PODs.

> kubectl scale rs new-replica-set --replicas=5

```replicaset.apps/new-replica-set scaled```
> kubectl get replicaset

```
NAME              DESIRED   CURRENT   READY   AGE
new-replica-set   5         5         5       12m

```

#### 14) Now scale the ReplicaSet down to 2 PODs.

> kubectl scale rs new-replica-set --replicas=2

``` replicaset.apps/new-replica-set scaled ```

> kubectl get replicaset

```

NAME              DESIRED   CURRENT   READY   AGE
new-replica-set   2         2         2       12m

```
