# ChangeLog

CHANGELOG.md is Initialized for tracking server/database changes.
- 2025-09-14 - sudo dnf upgrade -y on .12 server to update all packages
- 2025-09-14 - sudo mkdir -p /srv/pgdata on .12 server to make the main database folder
- 2025-09-14 - sudo mkdir -p /srv/pgbackups on .12 server to make the main backup folder
- 2025-09-14 - sudo chown -R $USER:$USER /srv/pgdata /srv/pgbackups on .12 server to make scripts write inside folders
- 2025-09-17 - sudo dnf install -y podman on .12 server to install podman
- 2025-09-17 - podman --version on .12 server to ensure podman was install successfully (podman version 5.4.0)
- 2025-09-17 - podman volume create pgdata on .12 server for Postgres datbase files (managed by podman)
- 2025-09-17 - podman volume create pgbackups on .12 server for Postgres datbase files
- 2025-09-17 - sudo podman run -d \
  --name postgres \
  -e POSTGRES_USER=classadmin \
  -e POSTGRES_PASSWORD='PostgresPassword' \
  -e POSTGRES_DB=classdb \
  -v pgdata:/var/lib/postgresql/data \
  -v /srv/pgbackups:/backups \
  -p 0.0.0.0:5432:5432 \
  docker.io/library/postgres:15 on .12 server to run PostgreSQL container
- 2025-09-17 sudo podman exec -it postgres psql -U classadmin -d classdb on .12 server to connect into Postgres
