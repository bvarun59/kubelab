This is my kubelab repo


to install metric server for checking cpu and memory used by pod
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

kubectl top pods 

Metrics API not available

kubectl edit deployment metrics-server -n kube-system
unser args:
- --kubelet-insecure-tls


minikube start --driver=docker
#start minikube on restart

kubectl top node
kubectl top pod

kubectl get pods
kubectl exec -it <podname> -n <namespace> -- bash
kubectl logs myapp
kubectl describe pod myapp
kubectl port-forward pod/myapp -n <namespace> 8080:80
kubectl port-forward deployment/<deploymentname> -n <namespace> 8080:80

kubectl get deploy
kubectl get deploy -n <namespace>


kubectl get pods -n demodeployment -o wide
#get ip detailed information on pods

kubectl delete pods/mydeployment-65c964b6f5-wgfcb -n demodeployment
#delete pod from namespace

kubectl get service -n <namespace>

IMP:-
IN DEPLOYMENT MANIFEST FILE below details should be same
  selector:           and   template:    
    matchLabels:               metadata:
       app: nginx                labels:
                                    app: nginx

IN SERVICE MANIFEST FILE should be same , bcz service will apply for these label named pods
  selector:
    app: nginx

if you use type as ClusterIP, then you cant access outside , since its a private cluster network
for this to work again you have to map and execute 

for visual binding 
minikube service myservice -n demodeployment

ssh -L 30080:192.168.49.2:30080 varun@192.168.0.110
manually SSH tunnel: