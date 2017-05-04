# Docker CLI

* Basic docker CLI commands
* Manage containers

## Control Container
* run
* list
* daemon
* exec
* start/stop
* naming
* logs
* copy files

### Run

```
docker run --interactive --tty debian bash
ps axjf
ip a
hostname
cat /etc/resolv.conf
ping 172.17.0.1
ping google.com
```

### List

```
docker ps
docker ps -a
```
### Daemonize

```
docker run -it -d debian bash
```

### Exec

```
docker exec -it $(docker ps -ql) sh
ps axjf
```

### Start/Stop/Restart/Auto Restart

```
docker start <first_container_name>
docker ps -a
docker restart <first_container_ID>
docker stop <first_container_name>
```

### Naming

```
docker rename pedantic_bassi debian
```

### Logs

```
docker logs --tail=10 -f <container_name>
docker logs <container> | grep <search>
```

### Copy files

```
docker cp debian:/etc/passwd /tmp
```


## Control Images
* list
* search
* pull
* login
* commit
* tag
* push

### List

```
docker images
```

### Search

```
docker search redis
```

### Pull

```
docker pull redis
```

### Use private registry

```
docker login <private_registry>
```

### commit

```
docker exec -it debian bash
apt-get update
apt-get install ruby
ruby --version
docker commit debian <yourname>-ruby:debian
docker images
```

### Tag

```
dodcker tag <yourname>-ruby:debian docker-workshop.local/<yourname>-ruby:debian
```

### Push

```
docker push docker-workshop.local/<yourname>-ruby:debian
```


## Cleaning-up
* rm
* rmi

### Remove container

```
docker ps -a
docker rm debian
docker rm -f debian
```

### Remove image

```
docker images
docker rmi docker-workshop.local/<yourname>-ruby:debian
```


## Exercise

Create an image from your container

```
docker run -it ubuntu:14.04 bash
apt-get update
apt-get install nginx redis
docker commit <CONTAINER_NAME> docker.workshop.local/ali-app1
docker login docker.workshop.local
docker push docker.workshop.local/ali-app1
```
