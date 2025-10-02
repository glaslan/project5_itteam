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
  -e POSTGRES_PASSWORD='ProjectV2025' \
  -e POSTGRES_DB=classdb \
  -v pgdata:/var/lib/postgresql/data \
  -v /srv/pgbackups:/backups \
  -p 0.0.0.0:5432:5432 \
  docker.io/library/postgres:15 on .12 server to run PostgreSQL container
- 2025-09-17 - sudo podman exec -it postgres psql -U classadmin -d classdb on .12 server to connect into Postgres
- 2025-09-17 - sudo firewall-cmd --add-port=5432/tcp --parmanent on .12 server to open postgres port for remote access
- 2025-09-17 - sudo podman exec -it postgres bash on .12 server
- 2025-09-17 - echo "host all all 0.0.0.0/0 scram-sha-256" >> /var/lib/postgresql/data/pg_hba.conf on .12 server to allow any IP to connect, as long as they have use a password
- 2025-10-01 - sudo mkdir -p /etc/containers/env on .12 server to hold environment files for Quadlet-managed containers
- 2025-10-01 - sudo nano /etc/containers/env/postgres.env on .12 server to create environment file with Postgres variables
  - POSTGRES_USER=classadmin
  - POSTGRES_PASSWORD=ProjectV2025
  - POSTGRES_DB=classdb
- 2025-10-01 - sudo chmod 600 /etc/containers/env/postgres.env on .12 server to set permmision only for root user access
- 2025-10-01 - sudo nano /etc/containers/systemd/postgres.container on .12 server to create quadlet unit
- 

  
