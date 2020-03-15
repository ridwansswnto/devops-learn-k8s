# Check Cluster

Ssebelum mulai belajar, ada baiknya check cluster yang akan di gunakan

## Check status komponen

run this command `kubectl get cs` to check:
```
NAME                 STATUS    MESSAGE             ERROR
controller-manager   Healthy   ok
scheduler            Healthy   ok
etcd-0               Healthy   {"health":"true"}
```

## Check cluster info
run this command `kubectl cluster-info` to get:

```
Kubernetes master is running at https://192.168.0.10:6443
KubeDNS is running at https://192.168.0.10:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

```

## Check node
run this command `kubectl get nodes` to get:

```
NAME                 STATUS   ROLES    AGE    VERSION
master.ridwan.com    Ready    master   3d9h   v1.17.3
worker1.ridwan.com   Ready    <none>   3d9h   v1.17.3
worker2.ridwan.com   Ready    <none>   3d9h   v1.17.3
worker3.ridwan.com   Ready    <none>   3d9h   v1.17.3
```

## PoC Web server NGINX
run this command `kubectl run first-nginx --image=nginx --replicas=2 --port=80`
```
deployment.apps/first-nginx created
```

will create pod
```
kubectl get pods
NAME                           READY   STATUS    RESTARTS   AGE
first-nginx-79fb65f4f6-jnhsx   1/1     Running   0          2m11s
first-nginx-79fb65f4f6-xhrkw   1/1     Running   0          2m11s
```

and deployment like:
```
kubectl get deployment
NAME          READY   UP-TO-DATE   AVAILABLE   AGE
first-nginx   2/2     2            2           3m54s
```