# Kibana Helm Chart

## Installing

### Using Helm repository

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



