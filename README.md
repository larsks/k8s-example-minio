## Overlays

To deploy Minio and a Kubernetes service with no external access:

```
kubectl apply -k base
```

To deploy Minio with a NodePort service that exposes the API on port 30900 and the console on port 30990:

```
kubectl apply -k overlay/nodeport
```

To deploy Minio with an Ingress resource that exposes the API at `https://minio.apps.cluster1.house` and the console at `https://minio-console.apps.cluster1.house`:

```
kubectl apply -k overlay/ingress
```

(You would presumably want to change these hostnames to ones appropriate for your local environment.)

## Viewing the manifests

If you want to see the generated manifests *without* deploying them:

```
kubectl apply -k overlay/nodeport -o yaml --dry-run=client
```
