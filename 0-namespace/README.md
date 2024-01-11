## Export namespace template using kubectl
kubectl create ns mynamespace --dry-run=client -oyaml | tee namspace.yaml

## Apply Namespace template 
 kubectl apply -f namspace.yaml


 ## Get the namespace 
kubectl get ns mynamespace -oyaml

## Set the kube context default namepsace to `mynamespace`
kubectl config set-context --current --namespace=mynamespace
