## About
This is a basic app about some basic commands to use for docker

## Commands

### Pulling an image
`$ docker image pull httpd:alpine`

### Building an image from a Dockerfile
`$ docker build -t myapacheimg .`

### List images
`$ docker image ls`

### Starting up a container from built image
`$ docker run -it --name myWebContainer -p 8080:80 myapacheimg`

**Parameters:**
- **-it**: interactive and TTY
- **--name**: name of the container
- **-p**: port to be used in the host that matchs the exposed port in the container

For more details run:
`$ docker run --help`

### Accessing to container shell
Run the following command in another terminal
`$ docker exec -it myWebContainer sh`

### Removing container automatically after stop
`$ docker run -it --rm --name myWebContainer -p 8080:80 myapacheimg`

- **--rm**: Automatically remove the container when it exits

## Shared volume between host and container
`$ docker run -it --rm --name myWebContainer -p 8080:80 -v $PWD/public-html:/usr/local/apache2/htdocs/ myapacheimg`

- **-v**: hostPath:ContainerPatch

## Define and run multi-container applications with docker-compose.yml

### Create and start containers
`$ docker-compose up`

### Stop and remove containers, networks, images, and volumes
`docker-compose down`

## Help!
Don't forget to add --help after `docker`, `docker run` or `docker-compose` to get help from the command