# Once Campfire Community Applications Template

This repository provides an [Unraid](https://unraid.net/) Community Applications template for [Campfire](https://github.com/basecamp/once-campfire), Basecamp's open source, single-tenant chat application. The template pulls the official image published at `ghcr.io/basecamp/once-campfire` and exposes basic configuration options for running Campfire on an Unraid server.

## Using the template

1. In Unraid, open the **Apps** tab and go to **Settings → Template repositories**.
2. Add this repository's URL and click **Save**.
3. Search for "Once Campfire" in the Apps tab and install it.

The container listens on ports **80** (HTTP) and **443** (HTTPS) and stores persistent data under `/rails/storage`.

## Environment variables

The template exposes common configuration variables:

| Variable | Description |
|----------|-------------|
| `SECRET_KEY_BASE` | Rails secret used to verify signed cookies. *Required*. |
| `SSL_DOMAIN` | Domain name for automatic Let's Encrypt certificates. |
| `DISABLE_SSL` | Set to `1` to serve HTTP without TLS. |
| `VAPID_PUBLIC_KEY` / `VAPID_PRIVATE_KEY` | Keys for Web Push notifications. |
| `SENTRY_DSN` | Optional DSN for reporting errors to Sentry. |

Map a volume to `/rails/storage` to persist the database and uploaded files.

## License

The Unraid template and documentation are released under the [MIT License](LICENSE). This license does **not** apply to Campfire itself, which is developed and licensed separately by Basecamp.
