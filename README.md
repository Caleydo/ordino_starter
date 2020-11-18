# Ordino Starter with AWS DocumentDB

This branch replaces the MongoDB Docker container with a remote [AWS DocumentDB](https://aws.amazon.com/de/documentdb/).
Please note that this example only works within a [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/de/vpc/).
In order to connect from your local computer follow the instructions from [Connecting to an Amazon DocumentDB Cluster from Outside an Amazon VPC](https://docs.aws.amazon.com/documentdb/latest/developerguide/connect-from-outside-a-vpc.html) first.

## Prerequisites

* Install [Docker](https://www.docker.com/)
* In the *config.json*, replace the *username*, *password*, and the *cluster URL* in both mongo connection strings
* Download the [Amazon DocumentDB Certificate Authority (CA)](https://s3.amazonaws.com/rds-downloads/rds-combined-ca-bundle.pem) as *rds-combined-ca-bundle.pem* into this directory

## Run

1. Run `docker-compose up` in your terminal
2. Navigate to [localhost:8080](http://localhost:8080) in your web browser
3. Login with username `admin` and password `admin`
