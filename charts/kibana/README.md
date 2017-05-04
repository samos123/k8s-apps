# Kibana

## Overview

Kibana is an open source analytics and visualization platform designed to work with Elasticsearch.
You use Kibana to search, view, and interact with data stored in Elasticsearch indices.
You can easily perform advanced data analysis and visualize your data in a variety of charts, tables, and maps.

Kibana makes it easy to understand large volumes of data. Its simple, browser-based interface enables
you to quickly create and share dynamic dashboards that display changes to Elasticsearch queries in real time.

Setting up Kibana is a snap. You can install Kibana and start exploring your Elasticsearch indices in
minutes — no code, no additional infrastructure required.

## Install chart

```console
helm install .
```

## Chart configuration

| Value | Description | Default |
| --- | --- | --- |
| component | Service name | logstash |
| port | Service port | 5043 |
| HTTPPort | HTTP port for service | 80 |
| protocol | Protocol to connect to service | TCP |
| replicas | Deployment replicas | 1 |
| elasticsearch.service | Elasticsearch service name to connect | elasticsearch-elasticsearch |
| elasticsearch.port | Elasticsearch service port to connect | 9200 |
| elasticsearch.preserveHost | If "true" will send the hostname specified in elasticsearch. If "false", then the host is used to connect to *this* Kibana instance will be sent | true |
| elasticsearch.requestTimeout | Time in milliseconds to wait for responses from the back end or Elasticsearch | 30000 |
| elasticsearch.shardTimeout | Time in milliseconds for Elasticsearch to wait for responses from shards. Set to 0 to disable | 0 |
| elasticsearch.startupTimeout | Time in milliseconds to wait for Elasticsearch at Kibana startup before retrying | 5000 |
| image.repository | Container image repository | 127.0.0.1:31500/kibana |
| image.tag | Container image tag | latest |
| image.pullPolicy | Container pull policy | Always |
| resources.requests.memory | Container requested memory | 2Gi |
| resources.requests.cpu | Container requested cpu | 250m |
| service.type | Type of service. Allowed values: ClusterIP, NodePort, LoadBalancer | ClusterIP |
| service.nodePort | (Optional) If type is NodePort, service uses specified node port | - |
| service.loadBalancerIP |(Optional) If type is LoadBalancer, service uses specified IP | - |
| ingress.enabled | Enable ingress for this chart or not | false |
| ingress.annotations | (Optional) Ingress annotations | - |
| ingress.hosts | (Optional) Ingress hostnames. Must be provided if Ingress is enabled | - |