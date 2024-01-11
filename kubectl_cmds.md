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

<details><summary>Set the kube context default namepsace to `mynamespace`</summary>
<p>

```bash
kubectl config set-context --current --namespace=mynamespace
```

</p>
</details>



 