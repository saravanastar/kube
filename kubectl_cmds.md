# Kubectl commands

## namespace
<details><summary>List namespace</summary>
<p>

```bash
kubectl get namespace
```

</p>
</details>

<details><summary>Create namespace</summary>
<p>

```bash
kubectl  create ns {namespace-name}
```

</p>
</details>
<details><summary>Delete namspace</summary>
<p>

```bash
kubectl delete ns {namespace-name}
```

</p>
</details>

<details><summary>Set the kube context default namepsace </summary>
<p>

```bash
kubectl config set-context --current --namespace={namespace}
```

</p>
</details>

## Pod
<details><summary>List Pod</summary>
<p>

```bash
kubectl get pods
```

</p>
</details>
<details><summary>Delete Pod</summary>
<p>

```bash
kubectl delete pod/{podname}
```

</p>
</details>
<details><summary>Execute command into the Pod</summary>
<p>

```bash
kubectl exec -it {podname} -- bash
```


</p>
</details>

<details><summary>Print env variable of the Pod</summary>
<p>

```bash
kubectl exec -it {podname} -- env
```

</p>
</details>

<details><summary>Filter the pods with the lable name</summary>
<p>

```bash
kubectl get pods -l {label}
```

e.g

```bash
kubectl get pods --selector app=webapp
```

```bash
kubectl get pods -l app=webapp
```

</p>
</details>

<details><summary>Filter the pods with the lable name</summary>
<p>

```bash
kubectl get pods -l {label}
```

e.g

```bash
kubectl get pods --selector app=webapp
```

```bash
kubectl get pods -l app=webapp
```

</p>
</details>
<details><summary>Create the pod named web with the name nginx</summary>
<p id="pod-creation">

```bash
kubectl run web --image=nginx --restart=Never
```

e.g

```bash
kubectl run web --image=nginx --restart=Never --labels app=web --env env1=value1 --annotations annoatation1=value1
```

</p>
</details>

<details><summary>Output the yaml of the pod without creating it</summary>
<p>

```bash
kubectl run web --image=nginx --restart=Never --dry-run=client -oyaml
```

e.g

```bash
kubectl run web --image=nginx --restart=Never -l app=web --env env1=value1 --annotations annoatation1=value1 --dry-run=client -oyaml
```

</p>
</details>

## Service
<details><summary>List the Service</summary>
<p>

```bash
kubectl get svc
```


</p>
</details>

<details><summary>Describe the Service</summary>
<p>

```bash
kubectl describe svc/{service-name}
```


</p>
</details>

<details><summary>Delete the Service</summary>
<p>

```bash
kubectl delete svc/{service-name}
```


</p>
</details>

<details><summary>Expose a pod with NodePort</summary>
<p>

```bash
kubectl expose {{podname}} --port=80 --target-port=80 --type=NodePort
```

e.g

```bash
kubectl expose pod/web --port=80 --target-port=80 --type=NodePort
```

to access the service node port in minikube
```bash
minikube service web --url
```
 Hit the dispalyed url in browser or curl, it should display/print the nginx welcome page.

</p>
</details>

<details><summary>Expose a pod with ClusterIp</summary>
<p>

```bash
kubectl expose {{podname}} --port=80 --target-port=80 --type=ClusterIP
```

e.g

```bash
kubectl expose pod/web --port=80 --target-port=80 --type=ClusterIP
```


</p>
</details>

<details><summary>Port forward to localhost</summary>
<p>

```bash
kubectl port-forward svc/{service-name} {host-port}:{service-port}
```

e.g

earlier step 
- [pod-creation](#pod-creation)

```bash
kubectl port-forward svc/web 8080:80
```

Curl to access the page
```bash
curl http://localhost:8080```

</p>
</details>




 