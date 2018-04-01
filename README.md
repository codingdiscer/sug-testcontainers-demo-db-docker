# Testcontainers db docker



## Database instance details

Upon spinning up the image, a single schema and table are created.  The details of the table can be found in the [init script](init-db.sh).

Here's some more relevant info about the postgres instance:

| Aspect | Detail |
| --- | --- |
| Database / Schema name | postgres |
| Username | postgres |
| Password | postgres |


## Build and run the base image

Kick off the docker image with the following command:

```
$ docker build -f Dockerfile-base -t sug-testcontainers-demo-db:base .
$ docker run -p 5432:5432 --name sug-testcontainers-demo-db-base -itd sug-testcontainers-demo-db:base
$ docker ps
```


## Build and run the test data image

Kick off the docker image with the following command (will run the db on port 5433):

```
$ docker build -f Dockerfile-testdata -t sug-testcontainers-demo-db:testdata .
$ docker run -p 5433:5432 --name sug-testcontainers-demo-db-testdata -itd sug-testcontainers-demo-db:testdata
$ docker ps
```
