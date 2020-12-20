# Mongodb on docker

steps are similar to postgres.

## Install Clients

```
sudo apt-get install mongodb-clients
```

## create a folder for persistance

```
mkdir -p $HOME/docker/volumes/mongo
```

## Run

```
docker run -d -p 27017:27017 -v ~/docker/volumes/mongo:/data/db mongo
```

try conencting

```
mongo localhost/mydb
```

### docker-compose
```
# Use root/example as user/password credentials
version: '3.1'

services:

  mongo:
    image: mongo
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example

  mongo-express:
    image: mongo-express
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: example
 ```
