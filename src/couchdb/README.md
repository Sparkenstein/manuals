# COUCHDB

```
docker run -p 5984:5984 -v ~/docker/volumes/couchdb:/opt/couchdb/data -e COUCHDB_USER=admin -e COUCHDB_PASSWORD=password --name couchdb -d couchdb
```
