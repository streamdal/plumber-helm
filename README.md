
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
helm install plumber batch/plumber

```

#### Standalone

```
helm repo add batch https://batchcorp.github.io/plumber-helm
helm repo update
helm install plumber-standalone batch/plumber-standalone
```

### Connect to plumber server
```
kubectl port-forward service/plumber 9091:9091
```
