# Elasticsearch Helm Chart

```
helm install --name elasticsearch --set resources.requests.cpu=100m ./elasticsearch
```

- Overriding CPU requests in your custom `values.yaml` file:
```
resources:
  requests:
    cpu: "100m"
```
