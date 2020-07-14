# Setup neo4j in docker

- create volume `mkdir ~/docker/volumes/neo4j`
- run
```sh
docker run --name neo4j \
-p 7474:7474 -p 7687:7687 \
-d \
-v ~/docker/volumes/neo4j/data:/data \
-v ~/docker/volumes/neo4j/logs:/logs \
-v ~/docker/volumes/neo4j/import:/var/lib/neo4j/import \
-v ~/docker/volumes/neo4j/pugins:/plugins \
--env NEO4J_AUTH=neo4j/test \
neo4j:latest
```

Done apparently 