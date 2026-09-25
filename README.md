# Workshop Shop

A small, editable ecommerce application for workshops. It has a browser frontend, shop API, PostgreSQL database, PostgREST data gateway, and separate mock payment service. The application source is mounted into prebuilt Node containers, so there are no application image builds.

## Run locally

To start the app:

```bash
make up
```

To stop the app:

```bash
make down
```

`db/init.sql` only runs on a fresh database volume. After changing it, run `make clean` (this wipes carts).

### OTel

If you want OTel, use:

```bash
# Paste your values — the endpoint can also be fetched by the CLI
export OTEL_EXPORTER_OTLP_ENDPOINT="https://<your-endpoint-from-bluebox-setup>"

# Paste the full header value from Bluebox Setup (do not include angle brackets)
export OTEL_EXPORTER_OTLP_HEADERS="<header value from Bluebox Setup>"

# Start the app (pulls images, waits for readiness)
make up
```
