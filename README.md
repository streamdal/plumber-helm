
### Test Run
```
helm install --dry-run --debug ./plumber-cluster --generate-name
helm install --debug ./plumber-cluster --generate-name
```

### Deploy from repo


#### Cluster mode

```
helm repo add batch https://streamdal.github.io/plumber-helm
helm repo update
helm show values batch/plumber-cluster > values.yaml
helm install -f values.yaml plumber batch/plumber-cluster

```

#### Standalone

```
helm repo add batch https://streamdal.github.io/plumber-helm
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

##### WASM Beta

```
git checkout plumber/wasm
cd plumber-helm
helm install -f wasm-beta-values.yaml plumber-wasm-ha ./plumber-cluster
kubectl port-forward svc/plumber-wasm-ha-plumber-cluster 9191:9191
```
