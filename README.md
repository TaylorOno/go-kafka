# Kafka

```powershell
kind create cluster -n cluster-1

helm install kafka oci://registry-1.docker.io/bitnamicharts/kafka --set metrics.kafka.enabled=true --set metrics.kafka.image.registry=docker.io --set metrics.kafka.image.repository=bitnami/kafka-exporter

podman build -f .\Dockerfile-producer -t kafka-producer:1.0.0 .
podman build -f .\Dockerfile-consumer -t kafka-consumer:1.0.0 .
```