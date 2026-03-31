# Homelab Services

A collection of services I have running in my homelab.

## Getting Started

Create a Docker network for the observability stack:

```bash
docker network create monitoring
```

Clone the repository onto the server:

```bash
git clone https://github.com/rynhndrcksn/homelab-services.git /srv/services && cd /srv/services
```

Go into each directory and start up the `docker-compose.yml` file:

```bash
cd caddy && docker compose up -d
```

### First Time Setup

Ensure you have all the directories and file permissions setup properly:

```bash
mkdir -p /mnt/data/{prometheus,loki,grafana,caddy/data,caddy/config}
chown -R 472:472 /mnt/data/grafana
chown -R 10001:10001 /mnt/data/loki
chown -R 65534:65534 /mnt/data/prometheus
```

During the first set up, the observability stuff needs to be started in a specific order:

```bash
cd /srv/services/loki && docker compose up -d
cd /srv/services/prometheus && docker compose up -d
cd /srv/services/node-exporter && docker compose up -d
cd /srv/services/cadvisor && docker compose up -d
cd /srv/services/alloy && docker compose up -d
cd /srv/services/grafana && docker compose up -d
cd /srv/services/caddy && docker compose up -d
```

## Contributing

If you see a problem or improvement that can be made, please open up an issue to discuss it.

## License

Copyright© 2026 Ryan Hendrickson. Released under the BSD-3-Clause License. See [LICENSE](LICENSE) for details.
