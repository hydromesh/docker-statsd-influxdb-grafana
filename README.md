# Docker service with Telegraf (StatsD), InfluxDB and Grafana

:facepunch: Battle-tested

## Versions

* Main version:      3.0.0
* InfluxDB:          2.5.1
* Telegraf (StatsD): 1.24.3
* Postgres:          14.2.0
* Grafana:           9.2.3


## Quick Start

First download and install the latest available version of Docker Compose <https://docs.docker.com/compose/install/>

In order to start the service the first time launch:

```sh
COMPOSE_PROFILES=grafana,telegraf docker-compose up -d
```

You can replace `COMPOSE_PROFILES=grafana,telegraf` with the desired profiles to launch, you can launch only InfluxDB (default with no profiles).

To stop the service launch:

```sh
COMPOSE_PROFILES=grafana,telegraf docker-compose down
```

## Mapped Ports

```
Host		Container		Service

3003		3003        grafana
8086		8086        influxdb
8125		8125        statsd
```

## Grafana

Open <http://192.168.50.22:3003>

```
Username: root
Password: root
```

### Data source on Grafana

InfluxDB data source is automatically provisioned with new Flux language support flag.

## InfluxDB

### Web Interface

Open <http://192.168.50.22:8086>

```
Username: admin
Password: admin123456
Port: 8086
```

## Customizations

You can customize all settings in the attached config files, then you can stop and start the service in order to reload the new configurations.
