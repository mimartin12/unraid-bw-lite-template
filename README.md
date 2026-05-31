# Unraid Bitwarden Lite Template

This repository contains an unofficial Unraid Docker template for the official Bitwarden Lite self-hosted deployment.

This template is not supported, endorsed, or maintained by Bitwarden. It only wraps the official Bitwarden Lite container image for deployment on Unraid.

## Template

- `bitwarden-lite.xml`

## Defaults

- Image: `ghcr.io/bitwarden/lite:latest`
- Network: `bridge`
- Web UI: `https://[IP]:[PORT:8443]/`
- Data path: `/mnt/user/appdata/bitwarden-lite` mounted to `/etc/bitwarden`
- Logs path: `/mnt/user/appdata/bitwarden-lite/logs` mounted to `/var/log/bitwarden`
- Database provider: `sqlite`
- SSL: enabled by default

## Required setup

Before starting the container, set these template fields:

- `BW_DOMAIN`: the hostname or IP address users will use to reach Bitwarden.
- `BW_INSTALLATION_ID`: generated at https://bitwarden.com/host/.
- `BW_INSTALLATION_KEY`: generated at https://bitwarden.com/host/.

SQLite is the default database. To use MariaDB, MySQL, PostgreSQL, or MSSQL, change `BW_DB_PROVIDER` and fill in the advanced external database fields. Find more details on configuration by visiting the [offical docs](https://bitwarden.com/help/install-and-deploy-lite/).

## Sources

- Bitwarden Lite docs: https://bitwarden.com/help/install-and-deploy-lite/
- Bitwarden self-host repository: https://github.com/bitwarden/self-host/tree/main/bitwarden-lite
- Unraid Community Applications XML docs: https://ca.unraid.net/submit/help/repository-xml
