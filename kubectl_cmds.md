# Kubectl commands

## namespace
### List namespace
kubectl get namespace
### Create namespace
k create ns {namespace-name}
### Delete namspace
kubectl delete ns {namespace-name}
### Set the kube context default namepsace to `mynamespace`
kubectl config set-context --current --namespace=mynamespace

 