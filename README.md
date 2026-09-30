# Spring Cloud Service Discovery

Small Spring-based service-discovery and inter-service communication project.

## Architecture

```text
service-client --OpenFeign--> service-voiture
        \                         /
         \---- Eureka Server -----/

Prometheus <--- application metrics ---> Grafana
```

The repository contains an Eureka server, a client service, and a vehicle service. `service-client` includes an OpenFeign client for calling `service-voiture`.

## Observability and Load Testing

`prometheus.yml`, Grafana provisioning files, and `test_plan.jmx` are included for metrics visualisation and JMeter-based load testing. Docker Compose currently provisions Prometheus and Grafana; application services are configured in their own modules.

## Getting Started

1. Build each Maven module.
2. Start Eureka Server, then the application services.
3. Start the monitoring stack with `docker compose up`.
4. Import or run `test_plan.jmx` with JMeter when load testing is required.

## Service Discovery

The checked-in configuration demonstrates Eureka. No Consul configuration is documented in this repository.
