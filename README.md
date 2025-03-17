### ArgoCD
For installing argocd in the cluster, use the following commands
```
kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

---

And then, port-forward the argocd-server service to 443 and login into the argocd-dashboard.

```
kubectl port-forward -n argocd svc/argocd-server 4000:443
```

Now, open the browser at **https://localhost:443** and continue to the dashboard using advanced option.

By default, username is admin and password is saved in a secret file named **argocd-initial-admin-secret**
```
k get secret argocd-initial-admin-secret -n argocd -o yaml
```

Get the secret and decode it using base64 and login to the dashboard.