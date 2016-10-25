**NOTE:** 

Local paths have to be relative. Absolute paths don't work.

### Create docker image

`docker build -t dineshs91/cqrs .`

### List docker images

`docker images`

### Create a container and forward port

`docker run -d -p 8000:8000 dineshs91/cqrs`

### Status of the docker containers

`docker ps -a`

### Stop a container

`docker stop <container-id>`

### Remove containers

`docker rm <container-id>`

### Remove all containers

`docker rm $(docker ps -aq)`

### Remove docker images

`docker rmi <image-id>`

### Add a tag to a docker image

`docker tag <image-id> dineshs91`

### Get a bash shell for the container

`docker exec -it <container-id> /bin/bash`

### Check the logs of a container

`docker logs <container-id>`

## Docker compose

### Run docker compose in detached mode

`docker-compose up -d`

### Get a shell from docker compose

`docker-compose run web bash`

### Bring the containers up (After rebuild)

`docker-compose up --build`

### Status of the containers from compose

`docker-compose ps`
