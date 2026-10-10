# Network service boundaries

Upstream provenance is recorded in [UPSTREAM.json](UPSTREAM.json). The upstream MIT license is retained in [LICENSE](LICENSE).

The nginx implementations retain their upstream protocols. DiamaneOS changes endpoint names, publication bindings and Debian integration. Geocoding and website publication are excluded; authoritative DNS is external.

Deployment uses [DiamaneOS/infrastructure](https://github.com/DiamaneOS/infrastructure/tree/main/debian). Targets are supplied explicitly. Inherited fleet installation scripts are outside that Debian deployment path.

The nginx runtime uses stream and gzip-static modules without a separately rebuilt Brotli module. Requests have bounded inputs, I/O threads and timeouts. Request logs are disabled.

API listeners require TLS 1.3. The SUPL listener also permits TLS 1.2 with ECDHE and AEAD ciphers. Session tickets rotate through the shared infrastructure scripts. DNS resolution uses systemd-resolved.
