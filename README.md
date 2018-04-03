# Microservices
## Docker
```docker-1.log``` contains result of ```docker images``` command.
```mnikolaenko/ubuntu-tmp-file``` image is build upon the base ubuntu image +
temp file with "Hello world".

Dockerfile describes app container build. The build of the container includes
installation of mongo db, app requirements, downloading app code from repo
copying configs and initial script.
