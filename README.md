# Spring Prometheus demo application

Simple demo application that exposes a Prometheus metrics endpoint
an `actuator/prometheus`.

## Build

```
mvn clean package
```

## Create container image

```
mvn spring-boot:build-image
docker tag prometheus-demo:0.0.1-SNAPSHOT <your-repo>/prometheus-demo
docker push <your-repo>/prometheus-demo
```

## Deploy to Kubernetes

Adapt container image name in [deployment.yaml](./kubernetes/deployment.yaml) 
according to your registry (or use the existing one).

```
kubectl apply -f ./kubernetes/deployment.yaml
```
