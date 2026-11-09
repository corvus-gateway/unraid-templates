# Corvus AWPG — Unraid templates

Unraid Community Applications templates for [Corvus AWPG](https://corvusgateway.org/), a self-hosted
web gateway: reverse proxy with free Let's Encrypt certificates, attack blocking, a traffic monitor
and an access queue.

| Template | Image |
|---|---|
| [`templates/corvus.xml`](templates/corvus.xml) | `ghcr.io/corvus-gateway/gateway:latest` |

## Install

In Unraid, open **Apps**, search for **Corvus** and click **Install**.

- The admin console is on port **9443** (HTTPS, self-signed certificate at first).
- Unraid's web interface usually uses ports 80 and 443, so the template publishes Corvus on
  **1880** (HTTP) and **18443** (HTTPS). Forward 80 → 1880 and 443 → 18443 on your router, or give
  the container its own IP address (br0 or a custom network) and use 80/443 directly.
- The one-time setup token for the first sign-in is in the container log (look for `setup_token`),
  or set **Setup Token** before the first start.
- Data is kept in `/mnt/user/appdata/corvus`. Back it up, especially `secrets/`.

Documentation: <https://corvusgateway.org/getting-started/nas/>

## Support

Questions and problems: [GitHub Discussions](https://github.com/corvus-gateway/corvus/discussions)
or [issues](https://github.com/corvus-gateway/corvus/issues) of the main repository.

## License

Apache License 2.0 — see [LICENSE](LICENSE).
