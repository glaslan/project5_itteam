# ChangeLog

CHANGELOG.md is Initialized for tracking server/database changes.
- 2025-09-14 - sudo dnf upgrade -y on .12 server to update all packages
- 2025-09-14 - sudo mkdir -p /srv/pgdata on .12 server to make the main database folder
- 2025-09-14 - sudo mkdir -p /srv/pgbackups on .12 server to make the main backup folder
- 2025-09-14 - sudo chown -R $USER:$USER /srv/pgdata /srv/pgbackups on .12 server to make scripts write inside folders
