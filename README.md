# Datadog Agent as Docker Container

## WHY this?

How to run Datadog agent to send metrics to datadog while running as a Docker container instead of on the host and how to hook all other services to the Datadog agent

## Description

A simple docker-compose configuration that allows the following services to run as docker containers

- prometheus
- grafana
- cadvisor
- consul
- node-exporter
- alert-manager sending alerts to datadog instead of slack

All the configuration items are there. Alert Manager rules can be extended and when new serivces are registered with Consul, Prometheus auto discovers the services.

## Installation

- Search for <DD_API_KEY> and replace that with your Datadog API key

```yaml
- DD_API_KEY=<DD_API_KEY>
```

```yaml
url: https://app.datadoghq.com/intake/webhook/prometheus?api_key=<DD_API_KEY>
```

- Run the following from the root folder

```bash
docker-compose up -d
```

- Run the following from the root folder to look at the status of the datadog agent

```bash
docker exec -it datadog agent status
```

## Removing the containers

- Run the following from the root folder

```bash
docker-compose down --remove-orphans
```

## URLs to access

- Prometheus available at [http://localhost:9090](http://localhost:9090)
- Consul available at [http://localhost:8500](http://localhost:8500)
- Alert Manager available at [http://localhost:9093](http://localhost:9093)
- Node Exporter available at [http://localhost:9100](http://localhost:9100)
- cadvisor available at [http://localhost:8080](http://localhost:8080)
- Grafana available at [http://localhost:3000](http://localhost:3000)

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
