# cka-prep-and-notes
* Kubernetes node static pod path:

browse the file: 
```sh
cat /var/lib/kubelet/config.yaml
```
* What is the IP of the CoreDNS server that should be configured on PODs to resolve services?

Run the command: 
```sh 
kubectl get service -n kube-system
``` 
and look for cluster IP value.

* Cluster domain name: 
can be found through this command: 
```sh
kubectl describe configmap coredns -n kube-system
```
