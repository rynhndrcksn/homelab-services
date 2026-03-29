# Homelab Services

A collection of services I have running in my homelab.

## Getting Started

Create a Docker network for the observability stack:

```bash
docker network create monitoring
```

Clone the repository onto the server:

```bash
git clone git@github.com:rynhndrcksn/homelab-services.git /srv/services && cd /srv/services
```

Go into each directory and start up the `docker-compose.yml` file:

```bash
cd caddy && docker compose up -d
```

## Contributing

If you see a problem or improvement that can be made, please open up an issue to discuss it.

## License

Copyright© 2026 Ryan Hendrickson. Released under the BSD-3-Clause License. See [LICENSE](LICENSE) for details.
