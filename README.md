[![Get it from the Snap Store](https://snapcraft.io/en/dark/install.svg)](https://snapcraft.io/haproxy-exporter)

# HAProxy Exporter Snap

A snap package for [haproxy_exporter](https://github.com/prometheus/haproxy_exporter) — a Prometheus exporter that scrapes HAProxy stats and exposes them via HTTP.

> **Note:** If possible, prefer the [built-in Prometheus exporter](https://www.haproxy.com/blog/haproxy-exposes-a-prometheus-metrics-endpoint/) available in HAProxy 2.0+.

## Install

```bash
sudo snap install haproxy-exporter
```

Metrics are exposed on `localhost:9101/metrics` by default.

## Configure

The snap supports these configuration options:

- `scrape-uri`: the URI of the HAProxy stats endpoint
- `web.listen-address`: the exporter listen address

The `?stats;csv` suffix is appended to `scrape-uri` automatically. Basic auth credentials can be embedded in the URI:

```bash
sudo snap set haproxy-exporter scrape-uri="http://user:pass@localhost:8404"
```

To change the exporter port while keeping it bound to localhost:

```bash
sudo snap set haproxy-exporter web.listen-address="localhost:9664"
```

Defaults:

- `scrape-uri`: `http://localhost:8404`
- `web.listen-address`: `localhost:9101`
