# Ordino Starter

## Prerequisites

* Install [Docker](https://www.docker.com/)

## Run

1. Run `docker-compose up` in your terminal
2. Navigate to [localhost:8080](http://localhost:8080) in your web browser

*Note* By default this Docker setup does not provide any data and the views might be empty or fail with an error. Hence, you must import your own data that is matching the Ordino schema. For more information please ask contact@caleydo.org.

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
