# docker-compose-example

### Prerequisite
1. [docker](https://www.docker.com/)
2. [docker-compose](https://docs.docker.com/compose/)

### Init
```bash
docker-machine create -d virtualbox dev
docker-machine create -d virtualbox live
```

### Use
```bash
eval "$(docker-machine env dev)"
docker-compose -f ex-redis-dev.yml up -d

eval "$(docker-machine env live)"
docker-compose -f ex-redis-live.yml up -d

curl http://$(docker-machine ip dev):5000
curl http://$(docker-machine ip dev):5000
curl http://$(docker-machine ip live):5000
```

### Cleanup
```bash
eval "$(docker-machine env dev)"
docker-compose -f ex-redis-dev.yml stop
docker-compose -f ex-redis-dev.yml rm

eval "$(docker-machine env live)"
docker-compose -f ex-redis-live.yml stop
docker-compose -f ex-redis-live.yml rm
```
