
### Test Run
```
helm install --dry-run --debug ./plumber --generate-name
helm install --debug ./plumber --generate-name
```

### Deploy from repo


#### Cluster mode

```
helm repo add batch https://batchcorp.github.io/plumber-helm
helm repo update
helm show values batch/plumber-cluster > values.yaml
helm install -f values.yaml plumber batch/plumber-cluster

```

#### Standalone

```
helm repo add batch https://batchcorp.github.io/plumber-helm
helm repo update
helm show values batch/plumber-standalone > values.yaml
helm install -f values.yaml plumber batch/plumber-standalone
```

### Connect to plumber server standalone 
```
kubectl port-forward service/plumber-plumber-standalone 9090:9090
```
### Connect to plumber server cluster

```
kubectl --namespace default port-forward svc/plumber-plumber-cluster 9090:9090

```
