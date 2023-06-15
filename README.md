# elasticsearch-docker
Docker Compose for Elasticsearch and Kibana


## Quickstart

Spin up es and kibana on docker

```yaml
docker-compose up -d
```

Access elasticsearch

```yaml
curl localhost:9200

{
  "name" : "c68da859ee27",
  "cluster_name" : "docker-cluster",
  "cluster_uuid" : "vtAnVtKoSHu_BGy3WFgnyg",
  "version" : {
    "number" : "7.10.1",
    "build_flavor" : "default",
    "build_type" : "docker",
    "build_hash" : "1c34507e66d7db1211f66f3513706fdf548736aa",
    "build_date" : "2020-12-05T04:58:07.655216Z",
    "build_snapshot" : false,
    "lucene_version" : "8.7.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}
```

Access kibana, [localhost:5601](http://localhost:5601) with your browser

Check volumes

```bash
docker volume ls

DRIVER    VOLUME NAME
local     es-docker_es-data
```

Get into ES container and check plugins list

```bash
# check container ID
docker ps

# get into container
docker exec -it <container_id> /bin/sh

./bin/elasticsearch-plugin list
```

stop & start containers

```bash
docker-compose stop
docker-compose up -d
```
