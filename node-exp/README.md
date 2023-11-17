# docker-monitoring-stack-gpnc
Grafana Prometheus Node-Exporter cAdvisor - Docker Monitoring Stack

## Makefile

[Note](https://docs.docker.com/compose/install/linux/): Due to `docker-compose` and the `compose` plugin, you might have one of the two installed. I have a `Makefile` that will detect which on you have installed.

You can list the targets using `make`.

## Boot

Boot the stack with docker compose (or `make up`):

```bash
docker-compose up -d
```

Ensure all containers are running:

```bash
docker-compose ps
```

The output should looke like this:

```bash
    Name                   Command                  State               Ports         
--------------------------------------------------------------------------------------
node-exporter   /bin/node_exporter --path. ...   Up             9100/tcp              
```

## Endpoints

The following endpoints are available:

| Container      | Internal Endpoint         | External Endpoint     |
| -------------- | ------------------------- |---------------------- |
| Node-Exporter  | http://node-exporter:9100 | http://localhost:9100 |

## Cleanup

To remove the containers using docker compose (or `make clean`):

```bash
docker-compose down
```

## Stargazers over time

[![Stargazers over time](https://starchart.cc/ruanbekker/docker-monitoring-stack-gpnc.svg)](https://starchart.cc/ruanbekker/docker-monitoring-stack-gpnc)

## Resources

Heavily inspired from [this exporter guide](https://grafana.com/oss/prometheus/exporters/node-exporter/)
