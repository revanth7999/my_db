# MySQL Docker Setup (`my_db`)

This project contains the Docker setup for running a standalone MySQL 8.0 database instance in a container with data persistence and shared networking support for use with other Dockerized applications.

---

 **Table of content:**

 - [Project Structure](#item-one)

 - [Project Setup](#item-two)

 - [Basic Table](#item-three)

<a id="item-one"></a>
## Project Structure

```bash
my_db/
├── docker-compose.yml
└── bin/
    └── connect.sh  # Shell script to connect to the DB
    └── in.sh  # Shell script to connect to the running docker container
```


<a id="item-two"></a>
## Project Set-Up

1. Create a Shared Docker Network (if not already created)

   Execute the below script to create a newtwork which will communicate to other docker apps

    ```bash
    docker network create my_shared_network
    ```
    This ensures containers across different projects can communicate over the same virtual network.
   
2. Start the MySQL Container

    Run the following command inside the my_db project root directory:
    ```bash
    docker compose up
    ```
    This will:
    - Start the MySQL 8.0 container named mybackend-db
    - Expose MySQL on host port 3307
    - Mount a named volume mysql-data for data persistence
    - Attach the container to the my_shared_network network

