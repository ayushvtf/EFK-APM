# ELK

Repo for maintaining helm charts of ELK stack and APM server

Install helm 

`brew install helm`


Once you have Helm initialized you can begin adding charts.



# Elasticsearch Helm Chart

```
helm install elasticsearch  ./elasticsearch
```

```
helm install  elasticsearch --set resources.requests.cpu=100m ./elasticsearch
```

- Overriding CPU requests in your custom values.yaml file:
```
resources:
  requests:
    cpu: "100m"
```


# APM Server Helm Chart

## Installing

* Install it
  ```
  helm install  apm-server ./apm-server
  ```

  ```
  helm install  apm-server elastic/apm-server --set imageTag=7.6.2
  ```




# Kibana Helm Chart

## Installing


### Using Helm repository

* Install it
  ```
  helm install  kibana ./kibana
  ```

### Using extra configuration

  ```
  helm install  kibana ./kibana --set imageTag=7.6.2 --set elasticsearchHosts=http://elasticsearch-master
  ```

   ```
  helm install  kibana ./kibana  --set service.type=LoadBalancer  --set resources.requests.cpu=500m --set resources.limit.cpu=500m 
  ```


# Fluentd

## Installing

kubectl create -f fluentd/fluentd.yaml
