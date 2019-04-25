# Docker

Important References:
- [Instalation on Linux](https://medium.com/@Grigorkh/how-to-install-docker-on-ubuntu-19-04-7ccfeda5935)
- [Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/)

## Basic Theory
- What is the difference of build, create and run.
- Images
- Containers (inclding the difference of a VM)

Elements
- Base Image
- Docker File
- Docker Composer


## Dockerfile Example

Basic configuration of a docker image.

```dockerfile
# redis from package manager
FROM alpine # alpine is a lightweight dist
RUN apk add --update redis # apk is a package manager
CMD [ "redis-server" ]
```

This 2nd example shows a trick to avoid the rebuild. Until the npm install there is less chance of changes, it means that we can skip several steps of the "mathroska" building process using the cache.

```dockerfile
# nodejs 
FROM nodejs:alpine # alpine is a lightweight version
WORKDIR /usr/app
COPY ./package.json ./ # package contains the list of dependencies
RUN npm install # install the dependencies
COPY ./ ./ # copy all the files
CMD [ "npm", "start" ] # executes the app
```

## Building

```shell
~: docker build [options] .
# Options:
# -t "app/container_name"
```

## Running
Running is quivalent to build and create an image and then start the container
```shell
~: docker run [options] IMAGE
~: docker run image-name # creates a docker container from a image
~: docker run -it image-name sh # executes the command sh inside the container
~: docker run -p 8080:8080 image-name # port forwarding host:container
```

## Creation

```shell
~: docker create [options] IMAGE
# Options:
# -a, --attach               	# attach stdout/err
# -i, --interactive          	# attach stdin (interactive)
# -t, --tty                  	# pseudo-tty
# --name NAME            		# name your image
# -p, --publish 5000:5000    	# port map
# --expose 5432          		# expose a port to linked containers
# -P, --publish-all          	# publish all ports
# --link container:alias 		# linking
# -v, --volume `pwd`:/app    	# mount (absolute paths needed)
# -e, --env NAME=hello       	# env vars

# Example
~: docker create --name app_redis_1 --expose 6379 redis:3.0.2
```

### Listing Containers

```shell
docker ps 
--all 						# list all containers executed
```

### Prune

```shell
docker system prune 		# cleans everything
docker volume prune
docker network prune
docker container prune
docker image prune
```



### Logs

```shell
docker logs CONTAINER-ID
```

### Stoping

```shell
docker stop CONTAINER-ID 	# try to stop gracefully
docker kill CONTAINER-ID 	# try to stop the container imediately
```

### Exec

Executes a command inside the container

```shell
docker exec -it CONTAINER-ID sh # sh is the shell  
```

