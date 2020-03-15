## POD
The pod is a group of one or more containers and the smallerst deployable unit in ukbernetes:
Each Pod is isolated by the following Linux namespaces:
a. The process ID (PID)
b. The network namespace
c. The interprocess communication (IPC)
d. The unix time share (UTS)

## LAB
we will create pod with 2 different container
create pod file and run with `kubectl create -f first-pod.yml`
check pod event with `kubectl describe pod first-pod | grep -A20 Events`
```
Events:
  Type    Reason     Age        From                         Message
  ----    ------     ----       ----                         -------
  Normal  Scheduled  <unknown>  default-scheduler            Successfully assigned default/first-pod to worker3.ridwan.com
  Normal  Pulling    2m29s      kubelet, worker3.ridwan.com  Pulling image "nginx"
  Normal  Pulled     2m24s      kubelet, worker3.ridwan.com  Successfully pulled image "nginx"
  Normal  Created    2m24s      kubelet, worker3.ridwan.com  Created container nginx
  Normal  Started    2m24s      kubelet, worker3.ridwan.com  Started container nginx
  Normal  Pulling    2m24s      kubelet, worker3.ridwan.com  Pulling image "centos"
  Normal  Pulled     2m20s      kubelet, worker3.ridwan.com  Successfully pulled image "centos"
  Normal  Created    2m20s      kubelet, worker3.ridwan.com  Created container centos
  Normal  Started    2m19s      kubelet, worker3.ridwan.com  Started container centos
```

now we access centos container with `kubectl exec first-pod -it -c centos -- /bin/bash` and curl:
```
 curl -I http://localhost:80
HTTP/1.1 200 OK
Server: nginx/1.17.9
```

kesimpulannya adalah pod menghubungkan 2 container yang berbeda dalam linux network namespace yang sama