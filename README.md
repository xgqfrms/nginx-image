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


## run 

```sh
$ docker build -t nginx-image .

# run container
# -d 分离模式 detached mode (in the background)
# -p 端口号, map port 3000 of the host to port 3000 in the container
# $ docker run -dp 3000:3000 getting-started-image

$ docker run -dp 80:80 nginx-image


http://localhost/
# OR
http://localhost:80/ OK

```

```sh
$ docker images

REPOSITORY               TAG       IMAGE ID       CREATED         SIZE
nginx-image              latest    f3b55eb2b316   3 minutes ago   158MB
xgqfrms/nginx-image      latest    26c8f0d56747   2 hours ago     158MB
getting-started-image    latest    7b610e25a98a   3 hours ago     180MB
nginx                    latest    ae2feff98a0c   12 days ago     133MB
docker/getting-started   latest    021a1b85e641   2 weeks ago     27.6MB
centos                   latest    300e315adb2f   2 weeks ago     209MB
ubuntu                   latest    f643c72bc252   4 weeks ago     72.9MB
xgqfrms/node.js          latest    973e880b15f5   3 months ago    155MB

```

```sh
$ docker run -dp 80:80 xgqfrms/nginx-image

```

## update remote image

```sh
# push ✅
$ docker push xgqfrms/nginx-image

```


```sh
 docker images
REPOSITORY               TAG       IMAGE ID       CREATED          SIZE
nginx-image              latest    f3b55eb2b316   10 minutes ago   158MB
xgqfrms/nginx-image      latest    f3b55eb2b316   10 minutes ago   158MB
xgqfrms/nginx-image      <none>    26c8f0d56747   2 hours ago      158MB
getting-started-image    latest    7b610e25a98a   3 hours ago      180MB
nginx                    latest    ae2feff98a0c   12 days ago      133MB
docker/getting-started   latest    021a1b85e641   2 weeks ago      27.6MB
centos                   latest    300e315adb2f   2 weeks ago      209MB
ubuntu                   latest    f643c72bc252   4 weeks ago      72.9MB
xgqfrms/node.js          latest    973e880b15f5   3 months ago     155MB

```


```sh
# pull
$ docker pull xgqfrms/nginx-image:latest

latest: Pulling from xgqfrms/nginx-image
Digest: sha256:5c5e8a85e97c2f744174f8c9d75ac53f84f87ecef6642ef0df112d328d8c430d
Status: Image is up to date for xgqfrms/nginx-image:latest
docker.io/xgqfrms/nginx-image:latest

```

docker.io/xgqfrms/nginx-image:latest
=> 
https://www.docker.com/xgqfrms/nginx-image:latest

http://localhost/

```sh
$ docker images                         
REPOSITORY               TAG       IMAGE ID       CREATED          SIZE
nginx-image              latest    f3b55eb2b316   16 minutes ago   158MB
xgqfrms/nginx-image      latest    f3b55eb2b316   16 minutes ago   158MB
xgqfrms/nginx-image      <none>    26c8f0d56747   2 hours ago      158MB
getting-started-image    latest    7b610e25a98a   3 hours ago      180MB
nginx                    latest    ae2feff98a0c   12 days ago      133MB
docker/getting-started   latest    021a1b85e641   2 weeks ago      27.6MB
centos                   latest    300e315adb2f   2 weeks ago      209MB
ubuntu                   latest    f643c72bc252   4 weeks ago      72.9MB
xgqfrms/node.js          latest    973e880b15f5   3 months ago     155MB

```


> no needs

```sh
# 关联 tag 不需要了，第一次已经自动关联上了 
$ docker tag f3b55eb2b316 xgqfrms/nginx-image

# push
$ docker push xgqfrms/nginx-image

```



