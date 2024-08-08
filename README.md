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
* ingress default backend

Execute the command 
```sh
kubectl describe ingress --namespace app-space
```
 and examine the Default backend field. If it displays ```<default>```, proceed to inspect the ingress controller's manifest by executing 
 ```sh
 kubectl get deploy ingress-nginx-controller -n ingress-nginx -o yaml
 ```
 In the manifest, search for the argument ```--default-backend-service```

* Pod cidr 
```sh
cat /etc/kubernetes/manifests/kube-controller-manager.yaml | grep cluster-cidr
```
* Service cidr 
```sh
cat /etc/kubernetes/manifests/kube-apiserver.yaml
```
