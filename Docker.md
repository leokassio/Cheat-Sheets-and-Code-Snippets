# Docker

### Building

```shell
docker build [options] .
-t "app/container_name"    	# name
```

### Running

```shell
docker run [options] IMAGE
# docker run = docker create + docker start
```

### Creation

```shell
docker create [options] IMAGE
-a, --attach               	# attach stdout/err
-i, --interactive          	# attach stdin (interactive)
-t, --tty                  	# pseudo-tty
--name NAME            		# name your image
-p, --publish 5000:5000    	# port map
--expose 5432          		# expose a port to linked containers
-P, --publish-all          	# publish all ports
--link container:alias 		# linking
-v, --volume `pwd`:/app    	# mount (absolute paths needed)
-e, --env NAME=hello       	# env vars
# Example
docker create --name app_redis_1 --expose 6379 redis:3.0.2
```

### PS

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

