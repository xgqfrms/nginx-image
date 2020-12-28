# nginx-image

> Docker Nginx Image

https://hub.docker.com/repository/docker/xgqfrms/nginx-image

## build image

```sh
# -t tag-image-name
# . current directory's Dockerfile
$ docker build -t nginx-image .

```

```sh
$ docker images

$ docker ps
# REPOSITORY               TAG       IMAGE ID       CREATED             SIZE
# nginx-image              latest    26c8f0d56747   4 minutes ago       158MB

```
## push

```sh
$ docker push xgqfrms/nginx-image

$ docker tag 26c8f0d56747 xgqfrms/nginx-image

```
## pull

```sh
$ docker pull xgqfrms/nginx-image:latest

```

