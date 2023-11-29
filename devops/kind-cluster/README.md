# Install Kind

[KIND install](https://kind.sigs.k8s.io/docs/user/quick-start/)

```
brew install kind
```
# Create Kind Cluster
```
kind create cluster --config=./kind-cluster.yaml

# verify cluster
kind get clusters

# delete cluster
kind delete clusters <cluster-name>
```
