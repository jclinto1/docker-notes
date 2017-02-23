# Docker Notes #

Bunch of docker commands and helpful reminders

### Build image ###

`docker build -t <name> .`

### Get the image id ###

`docker images -q <name> .`

### Login to Repo ###

`docker login <hostname:port>`

### Tag the image ###

`docker tag <id> <hostname:port>/<name>:latest`

### Push the image ###

`docker push <hostname:port>/<name>:latest`

### Run the image ###

`docker run -d <name>`

### Connect to the running container ###

`docker exec -it <id> /bin/bash`

### List all running containers ###

`docker ps`

### List all contains including stopped ###

`docker ps -a`

### Get logs  ###

`docker logs <id>`

### Delete all containers  ###

`docker rm $(docker ps -a -q)`

### Delete all images ###

`docker rmi $(docker images -q)`

### Find Docker IPAddresses ###

`docker inspect -f '{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $(docker ps -aq)`

### Copy Files off a Container ###

`docker cp <container_id>:<container_path> <host_path>`

`docker cp ec6ed1137c46:/tmp/app.log .`

# CI Command Conbinations 

### Build, Tag and Push Latest Image

`docker build -t jclinto1/ubuntu .`

`image_id=$(docker images -q jclinto1/ubuntu)`

`docker tag $image_id jclinto1/ubuntu:latest`

`docker push jclinto1/ubuntu:latest`

# Docker Compose #

### Start up in the foreground ###

`docker-compose up`

### Start up on anothter thread ###

`docker-compose up -d`

### Down the containers ###

`docker-compose down`

### Pull the containers ###

This is most useful when you have an integration server and you want to refresh it on a cron from your private Docker repo

`docker-compose pull`