# Ordino Starter with AWS DocumentDB and AWS ElastiCache

This branch replaces the MongoDB Docker container with a remote [AWS DocumentDB](https://aws.amazon.com/de/documentdb/) and the Redis container with a remote [AWS ElastiCache](https://docs.aws.amazon.com/elasticache/).

Please note that the AWS DocumentDB only works within a [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/de/vpc/).
In order to connect from your local computer follow the instructions from [Connecting to an Amazon DocumentDB Cluster from Outside an Amazon VPC](https://docs.aws.amazon.com/documentdb/latest/developerguide/connect-from-outside-a-vpc.html) first.

## Prerequisites

* Install [Docker](https://www.docker.com/)
* Download the [Amazon DocumentDB Certificate Authority (CA)](https://s3.amazonaws.com/rds-downloads/rds-combined-ca-bundle.pem) as *rds-combined-ca-bundle.pem* into this directory

## Configuration

The connection to the DocumentDB and ElastiCache can be configured in the *config.json*.
The following environment variables can be modified in the *docker-compose.yml*
and will be replaced in the *config.json* when launching the API container.

```yml
    environment:
      - REDIS_HOST=clusterName.xxxxxx.regionAndAz.cache.amazonaws.com
      - REDIS_USERNAME=foo
      - REDIS_PASSWORD=bar
      - MONGO_HOST=sample-cluster.node.us-east-1.docdb.amazonaws.com
      - MONGO_USERNAME=foo
      - MONGO_PASSWORD=bar
```

*Heads up!* The port is not part of the host and must be configured separately under `port` in the *config.json*.

In case the Redis connection requires a username and password, replace each `hostname` of the `phovea_data_redis` section in the *config.json* with `redis://REDIS_USERNAME:REDIS_PASSWORD@REDIS_HOST`.

## Run

1. Run `docker-compose up` in your terminal
2. Navigate to [localhost:8080](http://localhost:8080) in your web browser
3. Login with username `admin` and password `admin`
