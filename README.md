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

## IMAGE ID

> local vs remote

```sh
$ docker images
REPOSITORY               TAG       IMAGE ID       CREATED          SIZE
nginx-image              latest    26c8f0d56747   20 minutes ago   158MB
xgqfrms/nginx-image      latest    26c8f0d56747   20 minutes ago   158MB

getting-started-image    latest    7b610e25a98a   2 hours ago      180MB
nginx                    latest    ae2feff98a0c   12 days ago      133MB
docker/getting-started   latest    021a1b85e641   2 weeks ago      27.6MB
centos                   latest    300e315adb2f   2 weeks ago      209MB
ubuntu                   latest    f643c72bc252   4 weeks ago      72.9MB

```