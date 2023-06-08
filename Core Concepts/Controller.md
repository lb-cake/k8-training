# Controller

Watch Status 
Remediate Situate 
Node Monitor Period = 5s 
Node Monitor Grace Period = 40s 
POD Eviction Timeout = 5m 
 
This is typically the brain behind a lot of things in k8 
 
All the controllers are part of the Kube-Controller-Manager 
 
Kube-controller-manager.service 
 
View kube-controller-manager options - kubeadm 

```
cat /etc/kubernetes/manifests/kube-controller-manager.yaml 
 
cat /etc/system 
 
ps -aux | grep kube-controller-manager
```
