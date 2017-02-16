# Docker Notes

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