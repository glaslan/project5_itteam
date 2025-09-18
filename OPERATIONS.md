# Operations Guide

This file explains how to run, back up, restore, and maintain the PostgreSQL database 
- Database data: /srv/pgdata (.12 server)
- Database backups: /srv/pgbackups (.12 server)
- Access Database Inside Server: sudo podman exec -it postgres psql -U classadmin -d classdb
- Remote Access to Database: psql "host=10.172.55.12 port=5432 dbname=classdb user=classadmin password=ProjectV2025 sslmode=disable"
