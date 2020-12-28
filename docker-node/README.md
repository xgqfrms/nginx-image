# docker-lnpm

docker & lnpm

```sh
# -d - run the container in detached mode (in the background)
# -p 80:80 - map port 80 of the host to port 80 in the container
$ docker run -d -p 80:80 docker/getting-started
# OR
$ docker run -dp 80:80 docker/getting-started

```

## Dockerfile

http://localhost/tutorial/our-application/


```sh
FROM node:12-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]

```

Building the App's Container Image

```sh
# -t tag-image-name
# . current directory's Dockerfile
$ docker build -t getting-started-image .

```

Starting an App Container

```sh
# run container
# -d 分离模式 detached mode (in the background)
# -p 端口号, map port 3000 of the host to port 3000 in the container
$ docker run -dp 3000:3000 getting-started-image

```

http://localhost:3000/


```sh
$ docker ps

# CONTAINER ID
$ docker stop 91801b7162b4

```


node.js 3000

```js
const express = require('express');
const app = express();
const db = require('./persistence');
const getItems = require('./routes/getItems');
const addItem = require('./routes/addItem');
const updateItem = require('./routes/updateItem');
const deleteItem = require('./routes/deleteItem');

app.use(require('body-parser').json());
app.use(express.static(__dirname + '/static'));

app.get('/items', getItems);
app.post('/items', addItem);
app.put('/items/:id', updateItem);
app.delete('/items/:id', deleteItem);

db.init().then(() => {
    app.listen(3000, () => console.log('Listening on port 3000'));
}).catch((err) => {
    console.error(err);
    process.exit(1);
});

const gracefulShutdown = () => {
    db.teardown()
        .catch(() => {})
        .then(() => process.exit());
};

process.on('SIGINT', gracefulShutdown);
process.on('SIGTERM', gracefulShutdown);
process.on('SIGUSR2', gracefulShutdown); // Sent by nodemon


```

## ??? ❌

```sh
$ docker images
# REPOSITORY               TAG       IMAGE ID       CREATED       SIZE
# nginx-image              latest    26c8f0d56747   2 hours ago   158MB
# xgqfrms/nginx-image      latest    26c8f0d56747   2 hours ago   158MB
# getting-started-image    latest    7b610e25a98a   3 hours ago   180MB
# nginx                    latest    ae2feff98a0c   12 days ago   133MB
# docker/getting-started   latest    021a1b85e641   2 weeks ago   27.6MB
# centos                   latest    300e315adb2f   2 weeks ago   209MB
# ubuntu                   latest    f643c72bc252   4 weeks ago   72.9MB


# nginx-image
# xgqfrms/nginx-image

$ docker run -d -p 80:80 nginx-image
# OR
$ docker run -dp 80:80 nginx-image


$ docker run -d -p 80:80 xgqfrms/nginx-image
# OR
$ docker run -dp 80:80 xgqfrms/nginx-image

```

http://localhost/tutorial/


```sh
$ docker run -dp 3000:3000 nginx-image

$ docker run -dp 3000:3000 xgqfrms/nginx-image

```

