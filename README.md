# Docker compose example for Vue, Spring, Postgres

## Development Setup

```shell
mkdir postgres-database
docker-compose up
```

## Build production images

```shell
docker build -t spring-prod-example spring-backend/
docker build -t vue-prod-example spring-backend/
```

## Tag images and push to docker hub

Login to docker hub

```shell
docker login
```

Tag production images and push to repository.

```shell
docker tag vue-prod-example {YOUR_USERNAME}/vue-prod-example
docker tag vue-prod-example {YOUR_USERNAME}/spring-prod-example

docker push {YOUR_USERNAME}/vue-prod-example
docker push {YOUR_USERNAME}/spring-prod-example
```
