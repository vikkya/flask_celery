# flask_celery.

create docket network for redis
docker network create redis

docker run -it --rm --name redis --net redis -p 6378:6378 redis:7.2-alpine

docker run -it --rm --name redis --net redis -v ${PWD}/config:/etc/redis/ redis:7.2-alpine redis-server /etc/redis/redis.conf

## Security redis
requirepass PutSomeStrngPassword

change conf settings
appendonly yes

docker volume create redis
docker run -it --rm --name redis --net redis -v ${PWD}/config:/etc/redis/ -v redis:/data/ redis:7.2-alpine redis-server /etc/redis/redis.conf