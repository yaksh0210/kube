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
