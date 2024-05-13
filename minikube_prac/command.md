#### 1) > minikube start  ==> it will run minikube on container (here on docker container)

```
output:

😄  minikube v1.33.0 on Ubuntu 20.04
✨  Using the docker driver based on existing profile
👍  Starting "minikube" primary control-plane node in "minikube" cluster
🚜  Pulling base image v0.0.43 ...
🏃  Updating the running docker "minikube" container ...
❗  This container is having trouble accessing https://registry.k8s.io
💡  To pull new external images, you may need to configure a proxy: https://minikube.sigs.k8s.io/docs/reference/networking/proxy/
🐳  Preparing Kubernetes v1.30.0 on Docker 26.0.1 ...
🔎  Verifying Kubernetes components...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🌟  Enabled addons: storage-provisioner, default-storageclass
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

```


#### 2) > minikube status ==> it will show minikube status if it is running or not 

```
output:

minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

```

#### 3) > kubectl get nodes ==> it will show the list of nodes running in kuberenetes 

```
output:

NAME       STATUS   ROLES           AGE     VERSION
minikube   Ready    control-plane   4h49m   v1.30.0

```

#### 4) kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10 ==> it will create a deployment 

```
output:

deployment.apps/hello-minikube created
````
> kubectl get deployment

```
output:

NAME             READY   UP-TO-DATE   AVAILABLE   AGE
hello-minikube   0/1     1            0           18s

```
