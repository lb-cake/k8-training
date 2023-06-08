# Kube Scheduler

Scheduling Pods and Nodes 
 
Only responsible for decideing which pod to place on a node. 
The kubelet puts of the pod on the node, not the scheduler 
 
Filter Nodes that don't fit profile (memory or CPU resources) 
Rank Nodes (priority function) 
Calculates resources free after places pod 
 
 
You can install the kube-scheduler and extract it as a service 

```
cat /etc/kubernetes/manifests/kube-scheduler.yaml 
 
ps -aux | grep kube-scheduler
```
