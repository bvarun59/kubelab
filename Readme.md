This is my kubelab repo


to install metric server for checking cpu and memory used by pod
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

kubectl top pods 

Metrics API not available

kubectl edit deployment metrics-server -n kube-system
unser args:
- --kubelet-insecure-tls
