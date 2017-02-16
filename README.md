# docker-notes
Bunch of docker commands and helpful reminders

# Build image

`docker build -t <name> .`

# Get the image id #

`docker images -q <name> .`

# Login to Repo #

`docker login <hostname:port`

# Tag the image #

`docker tag <id> <hostname:port>/<name>:latest`

# Push the image #

`docker push <hostname:port>/<name>:latest`
