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
