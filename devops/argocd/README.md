#ArgoCD

### Install and Patch

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# turn off tls
kubectl patch configmap argocd-cm -n argocd --patch '{"data": {"server.insecure": "true"}}'

# restart argocd-server
kubectl rollout restart deploy argocd-server -n argocd

# open http://localhost:8080
kubectl port-forward svc/argocd-server -n argocd 8080:80

# get admin password
argocd admin initial-password -n argocd

kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d; echo

```