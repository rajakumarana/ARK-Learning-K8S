              Top                       Apply
Create  Scale       Explain   Set Edit             Diff
Expose  Autoscale   Describe  Get Delete 
        Rollout     logs

Cluster-info
Selector
Replace

Create: Kubectl create deployment <deployment-name> --image=<image-name>
Expose: Kubectl expose deployment <deployment-name> --port=8080 -- Type=LoadBalancer

Scale: Kubectl scale deployment <deployment-name> --replicas=3
Autoscale: kubectl autoscale deployment <deployment-name> --cpu-percent=70 --max=10
Rollout: kubectl rollout history deployment <deployment-name> 
         kubectl set image deployment <deployment-name> <container-name>=<image-name> --record=true
         kubectl rollout undo deployment <deployment-name> --to-revision=2

Explain: kubectl explain pods,replicaset,service,deployment
Describe: Kubectl describe pod <pod-name>/replicaset <repilca-set-name>/deployment <deployment-name>/service <service-name>
Logs: kubectl logs -f <pod-name>/<rs-name>

get: 
   kubectl get events
   kubectl get pod <pod-name>
   kubectl get nodes(no) <node-name>
   kubectl get rs <rs-name>
   kubectl get deployment <deployment-name>
   kubectl get service <service-name> -o wide
   kubectl get svc --watch

   kubectl get --all-namespaces(ns)/
   kubectl get -A
   kubectl get --namespaces=research/-n=research

   kubectl get pods --selector env=dev | wc -l
   kubectl get pods --selector env=dev  no-headers| wc -l
   
Set: kubectl set image deployment <deployment-name> <container-name>=<image-name>

Edit: kubectl edit deployment <deployment-name>
Delete: kubectl delete pod <pod-name>/replicaset <rs-name>/all -l app=<app-name>,deployment <deployment-name>

Top: kubectl top node/pod

Apply & get:

kubectl apply -f deployment.yaml
kubectl diff -f deployment.yaml
kubectl get deployment <deployment-name> -o yaml > deploy.yaml
kubectl get service <service-name> -o yaml > service.yaml

Cluster-info: kubectl cluster-info/cluster-info dump

Replace: kubectl replace --force -f nginx.yaml








