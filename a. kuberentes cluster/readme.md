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