# K8sWithHA
Create a K8s cluster with HA using keepalived and Haproxy. Read the Setup.txt file to know how to set up the cluster.

# After the configuration is done successfully the nodes and pods in the cluster looks like this:

NAME               STATUS   ROLES                  AGE    VERSION
kubecoordinator1   Ready    control-plane,master   167m   v1.20.2
kubecoordinator2   Ready    control-plane,master   163m   v1.20.2
kubecoordinator3   Ready    control-plane,master   121m   v1.20.2
kubehelper1        Ready    helper                 37m    v1.20.2
kubehelper2        Ready    helper                 36m    v1.20.2
kubehelper3        Ready    helper                 36m    v1.20.2

NAME                                       READY   STATUS    RESTARTS   AGE    IP              NODE               NOMINATED NODE   READINESS GATES
calico-kube-controllers-6dfcd885bf-4h7fk   1/1     Running   0          167m   172.16.56.195   kubecoordinator1   <none>           <none>
calico-node-4ww77                          1/1     Running   6          164m   10.9.208.245    kubecoordinator2   <none>           <none>
calico-node-6mxxg                          1/1     Running   0          122m   10.9.208.246    kubecoordinator3   <none>           <none>
calico-node-g42f7                          1/1     Running   0          167m   10.9.208.244    kubecoordinator1   <none>           <none>
calico-node-j89fc                          1/1     Running   0          37m    10.9.208.243    kubehelper3        <none>           <none>
calico-node-j9d27                          1/1     Running   0          38m    10.9.208.242    kubehelper2        <none>           <none>
calico-node-qhj25                          1/1     Running   0          38m    10.9.208.241    kubehelper1        <none>           <none>
coredns-74ff55c5b-8b5q8                    1/1     Running   0          168m   172.16.56.193   kubecoordinator1   <none>           <none>
coredns-74ff55c5b-d465h                    1/1     Running   0          168m   172.16.56.194   kubecoordinator1   <none>           <none>
etcd-kubecoordinator1                      1/1     Running   2          168m   10.9.208.244    kubecoordinator1   <none>           <none>
etcd-kubecoordinator2                      1/1     Running   0          157m   10.9.208.245    kubecoordinator2   <none>           <none>
etcd-kubecoordinator3                      1/1     Running   0          110m   10.9.208.246    kubecoordinator3   <none>           <none>
kube-apiserver-kubecoordinator1            1/1     Running   6          168m   10.9.208.244    kubecoordinator1   <none>           <none>
kube-apiserver-kubecoordinator2            1/1     Running   6          164m   10.9.208.245    kubecoordinator2   <none>           <none>
kube-apiserver-kubecoordinator3            1/1     Running   7          122m   10.9.208.246    kubecoordinator3   <none>           <none>
kube-controller-manager-kubecoordinator1   1/1     Running   1          168m   10.9.208.244    kubecoordinator1   <none>           <none>
kube-controller-manager-kubecoordinator2   1/1     Running   0          164m   10.9.208.245    kubecoordinator2   <none>           <none>
kube-controller-manager-kubecoordinator3   1/1     Running   0          122m   10.9.208.246    kubecoordinator3   <none>           <none>
kube-proxy-9fbkd                           1/1     Running   0          168m   10.9.208.244    kubecoordinator1   <none>           <none>
kube-proxy-b6h6v                           1/1     Running   0          37m    10.9.208.243    kubehelper3        <none>           <none>
kube-proxy-b7n82                           1/1     Running   0          122m   10.9.208.246    kubecoordinator3   <none>           <none>
kube-proxy-gvn8n                           1/1     Running   0          164m   10.9.208.245    kubecoordinator2   <none>           <none>
kube-proxy-q9l6l                           1/1     Running   0          38m    10.9.208.241    kubehelper1        <none>           <none>
kube-proxy-tjj89                           1/1     Running   0          38m    10.9.208.242    kubehelper2        <none>           <none>
kube-scheduler-kubecoordinator1            1/1     Running   1          168m   10.9.208.244    kubecoordinator1   <none>           <none>
kube-scheduler-kubecoordinator2            1/1     Running   0          164m   10.9.208.245    kubecoordinator2   <none>           <none>
kube-scheduler-kubecoordinator3            1/1     Running   0          122m   10.9.208.246    kubecoordinator3   <none>           <none>
