wp-docker-dev
===

a docker setup for developing wordpress themes.

### Getting Started

No need to install Wordpress stack, just run it all from docker.

```
# Build Customized Nginx Server
$ docker build -t nginx:cmng b_docker/nginx

# Starting up containers using `docker-compose.yml` context
docker-compose up -d

# Stopping a container
docker stop ${CONTAINER_NAME}

# Restarting a Container
docker restart ${CONTAINER_NAME}

# Restarting all running Containers
docker restart $(docker ps -a -q)

# Stopping all running Containers
docker stop $(docker ps -a -q)

# Stopping and Removing all running Containers
docker stop $(docker ps -a -q)  && docker rm $(docker ps -a -q)
```
