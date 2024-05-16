## Practice

> kubectl create -f service.yml 

``` service/myapp-service created ```

> kubectl get svc

```
NAME             TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE

hello-minikube   NodePort    10.96.233.212   <none>        8080:32558/TCP   2d7h
kubernetes       ClusterIP   10.96.0.1       <none>        443/TCP          3d4h
myapp-service    NodePort    10.105.151.70   <none>        80:30004/TCP     21m

```
>  minikube service myapp-service --url

``` http://192.168.49.2:30004 ```

