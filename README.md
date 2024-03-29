# Description

This project demonstrates the implementation of tasks related to software-defined systems, including sending Formula 1 car data to the cloud with Eclipse Kuksa and monitoring the cluster with Prometheus and Grafana. The project involves setting up Docker containers, deploying Prometheus and Grafana, and monitoring MQTT broker using Prometheus mosquitto-exporter.

# Task 1: Sending Formula 1 Car Data to Cloud with Eclipse Kuksa
## Docker Image Build and Push

`docker build -t docker-registry.rahti.csc.fi/kinzaghaffar/f1demo2val:latest -f Dockerfile .`

This command builds a Docker image for the f1demo2val application based on the provided Dockerfile.

`docker push docker-registry.rahti.csc.fi/kinzaghaffar/f1demo2val:latest`

This command pushes the built Docker image to the specified Docker registry.

## Docker Compose
`docker-compose up`

This command runs the Docker containers defined in the docker-compose.yml file, including kuksa.val, f1demo2val, and val2mqtt services.

## MQTT Subscription
`mosquitto_sub -t "kghaffar23/#" --cafile ca.crt --insecure --host mqtt.kghaffar23.rahtiapp.fi --port 443 -v`

This command subscribes to MQTT topics to receive messages from the MQTT broker for monitoring purposes.

# Task 3: Monitoring Cluster with Prometheus and Grafana
## Prometheus and Grafana Installation
`oc apply -f prometheus-grafana.yaml`

This command deploys Prometheus and Grafana to the cluster using the provided YAML configuration file.

## Monitoring MQTT Broker
This task involves installing Prometheus mosquitto-exporter and importing a Grafana dashboard to monitor the MQTT broker's uptime, traffic, and received messages.

## Dashboard Access
- Prometheus Dashboard:
- Username: admin
- Password: [provided password]
- [Prometheus Dashboard Link]

## Grafana Dashboard (Mosquitto Broker):
- Username: admin
- Password: [provided password]
- [Grafana Dashboard Link]

The project showcases the setup and monitoring of software-defined systems using Docker, Kubernetes, Prometheus, and Grafana.
