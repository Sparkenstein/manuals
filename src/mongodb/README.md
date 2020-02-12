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
