# Running postgres on Docker

## prerequisites

### Install Docker

Follow official steps

### Install psql client

```
sudo apt install postgresql-client-common postgresql-client-11
```

change version or command accordingly

### Install Posgres on docker

```
docker pull postgres
```

#### Create Volume for persistence

```
mkdir -p $HOME/docker/volumes/postgres
```

#### Run docker

```
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=postgres -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```

### Connect

```
psql -h localhost -U postgres -d postgres
```
