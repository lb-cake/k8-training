# Namespaces

Idea: Two people with same name, but they have different last names. In their house, they will address that person with their first name. 

Anyone outside of the house will address them buy their full name.

namespaces help differentiate between different pods with the same namespace.

THere is a default namespace. On startup, kubernetes creates pods to help manage k8...but that's in a namespace call, kube-system.

A third namespace, is kube-public is created automatically. This is where resources to be used by all users should be. 

If your cluster is small, you don't really need to worry about this. 

You can also use the same cluster for different resources. I.E. a dev namespace and prod namespace. Each namespace can have it's own policy and quota. 

Let's say you have 2 namespaces. Dev and Prod. But, you want to <b>specifically<b> use the dev service...

you could do something like...
mysql.connect("db-service.dev.svc.cluster.local")
when service is created, the DNS of the cluster creates this automatically. 
<service-name>.<namespace>.<service>.<domain>

```yaml
apiVersion: v1
kind: Namespace 
metadata:
    name: dev
```

```bash
kubectl create -f namespace-dev.yaml
kubectl create namespace dev
```

```bash
kubectl get pods --namespace=dev
kubectl config set-context $(kubectl config current-context) --namespace=dev
```

```bash
kubectl get pods --all-namespaces
```

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
    name: compute-quota
    namespace: dev
spec:
    hard:
        pods: "10"
        requests.cpu: "4"
        requests.memory: 5Gi
        limits.cpu: "10"
        limits.memory: 10Gi
```
