
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
helm install -f values.yaml plumber-standalone batch/plumber-standalone
```

### Connect to plumber server
```
kubectl port-forward service/plumber 9091:9091
```
