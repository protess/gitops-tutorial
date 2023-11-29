# Alipine toolxbox docker
## Usage
```
# to run a pod in k8s cluster
kubectl exec -it protess/alpine-toolbox -- /bin/sh

# to run a pod with pv example
kubectl apply -f debug-pod.yaml
```
## Included
- curl
- yq
- jq
- argocd-cli
- gh-cli
- git
- mycli


## Reference
[multi-arch-images](https://www.docker.com/blog/multi-arch-images/)