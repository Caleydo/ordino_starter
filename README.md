# Ordino Starter

## Prerequisites

* Install [Docker](https://www.docker.com/)


## Restore database dump

This Docker setup does not provide preloaded data for Ordino. Hence, the views of the default setup might be empty or fail with an error. Import your own data that is matching the Ordino schema or restore a backup. For more information please reach out to contact@caleydo.org.

1. Copy the PostgreSQL dump to *_backup* (e.g., `/backup/ordino.pgdump`)
2. Run `docker-compose up` in your terminal
3. Open a new terminal and run `docker-compose exec db_publicdb /bin/bash` to connect with the database container
4. Import database dump with `psql -h "localhost" -p "5432" -U "publicdb" publicdb < /backup/ordino.pgdump` (this might take a while)
5. Exit the container and the close the terminal

*Tip* You can confirm the import with by navigating to [localhost:8080](http://localhost:8080) or [PgAdmin](#PgAdmin).


## Run

1. Run `docker-compose up` in your terminal
2. Navigate to [localhost:8080](http://localhost:8080) in your web browser


## PgAdmin

PgAdmin can be used to import a database dump or administrate the PostgreSQL database.

1. Open http://localhost:5050/
2. Create a new server connection (right-click on server)
   - *General* tab
     - Name: publicdb (or any other name)
   - *Connection* tab
     - Hostname: db_publicdb
     - Port: 5432
     - Username: publicdb
     - Password: publicdb
3. Expand the newly created server connection
