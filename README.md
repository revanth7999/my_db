# MySQL Docker Setup (`my_db`)

This project contains the Docker setup for running a standalone MySQL 8.0 database instance in a container with data persistence and shared networking support for use with other Dockerized applications.

---

## Project Structure

```bash
my_db/
├── docker-compose.yml
└── bin/
    └── connect.sh  # Shell script to connect to the DB
