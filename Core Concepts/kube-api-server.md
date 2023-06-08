# Kube-API Server

Almost like the backend for the client 
 
1. Authenticate User 
2. Validate Request 
3. Retrieve Data 
4. Update ETCD 
5. Scheduler 
6. Kubelet 
 
It's the only component that updates the ETCD comonent 
 
The kube-api server is available to run the hard way 
 
To view the api-server options - kubeadm 
 
Cat /etc/kubernetes/manifests/kube-apiserve.yaml 
 
Cat /etc/systemd/system/kube-apiserver.service 
 
Ps -aux | grep kube-apiserver 
 
 
Controller Manager 
Takes action when a new ship leaves 
Manages containers that are damaged for fall off
