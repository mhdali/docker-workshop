# Dockerfile

## Redis

```
mkdir redis-fu; cd redis-fu
cat << EOF > Dockerfile
FROM ubuntu
RUN apt-get update && apt-get install -y redis-server redis-tools
EOF
docker build -t dockerws/redis-fu .
docker run dockerws/redis-fu redis-server
docker exec $(docker ps -ql) redis-cli info
```

## Wordpress

```
cd wordpress
wget https://wordpress.org/latest.zip
unzip -d wp latest.zip
docker build -t dockerws/wordpress .
docker run --rm -it -p 8080:80 dockerws/wordpress
```

## Cache

```
cd redis-fu
docker build -t dockerws/redis-fu .
docker build -t dockerws/redis-fu .
```

## gitignore

.dockerignore


