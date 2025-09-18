# Operations Guide

This file explains how to run, back up, restore, and maintain the PostgreSQL database 
- Database data: /srv/pgdata (.12 server)
- Database backups: /srv/pgbackups (.12 server)
- Access Database Inside Server: sudo podman exec -it postgres psql -U classadmin -d classdb
- Remote Access to Database: psql "
