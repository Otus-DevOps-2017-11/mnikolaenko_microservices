# Microservices
## Docker
```docker-1.log``` contains result of ```docker images``` command.
```mnikolaenko/ubuntu-tmp-file``` image is build upon the base ubuntu image +
temp file with "Hello world".

Dockerfile describes app container build. The build of the container includes
installation of mongo db, app requirements, downloading app code from repo
copying configs and initial script.

## reddit-microservices
```ui```, ```comment``` and ```post``` microservices are buit useing Dockerfiles
in ```reddit-microservices/<appropriate_service_name>```. Containers are
uploaded to dockerhub ```mnikolaenko/<container_name>```.

To start full application:
```
$ docker run -d --network=reddit --network-alias post_db --network-alias comment_db -v reddit_db:/data/db mongo:latest

$ docker run -d --network=reddit --network-alias post mnikolaenko/post:1.0

$ docker run -d --network=reddit --network-alias comment mnikolaenko/comment:1.0

$ docker run -d --network=reddit -p 9292:9292 mnikolaenko/ui:2.0
```

## docker-compose
Use ```docker-compose up -d``` to run all microservice containers. Configuration
is described in ```reddit-microservices/docker-compose.yml```. You should create
```.env``` file in ```reddit-microservices``` to define variables used in
```docker-compose.yml```.
