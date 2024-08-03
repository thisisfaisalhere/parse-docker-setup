# Running Parse Server + Postgres on Docker

This guide will walk you through the steps to run Parse Server on Docker.

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

- Docker: [Install Docker](https://docs.docker.com/get-docker/)

## Starting it up

```sh
docker-compose up -d
```

This will start up the server but make sure to have .env file

```text
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
PARSE_SERVER_APPLICATION_ID=divvyitup
POSTGRES_DB=${PARSE_SERVER_APPLICATION_ID}
PARSE_SERVER_MASTER_KEY=masterKey
PARSE_SERVER_DATABASE_URI=postgres://${POSTGRES_USER}:${POSTGRES_PASSWORD}@postgres/${POSTGRES_DB}
PARSE_DASHBOARD_SERVER_URL=http://localhost:9000/parse
PARSE_SERVER_MASTER_KEY_IPS=0.0.0.0/0
PARSE_DASHBOARD_APP_ID=${PARSE_SERVER_APPLICATION_ID}
PARSE_DASHBOARD_MASTER_KEY=${PARSE_SERVER_MASTER_KEY}
PARSE_DASHBOARD_APP_ID=${PARSE_SERVER_APPLICATION_ID}
PARSE_DASHBOARD_APP_NAME=DivvyItUp
PARSE_DASHBOARD_ALLOW_INSECURE_HTTP=1
PARSE_DASHBOARD_USER_ID=admin
PARSE_DASHBOARD_USER_PASSWORD=admin
```
