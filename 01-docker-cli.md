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
docker run -it -d nginx
```

### Exec

```
docker exec -it $(docker ps -ql) sh
ps axjf
```

### Start/Stop/Restart/Auto Restart

```
docker start <container_name>
docker ps -a
docker restart <container_ID>
docker stop <container_name>
```

### Naming

```
docker rename <container_name> debian
```

### Logs

```
docker logs --tail=10 -f <container_name>
docker logs <container_name> | grep <search>
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
docker pull busybox
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
docker commit <container_name> <yourname>-ruby
docker images
```

### Tag

```
dodcker tag <yourname>-ruby <yourname>-ruby:<ruby_version>
```

### Push

```
docker push mhdali/dockerws-ruby:2.1
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
docker rmi <yourname>-ruby
docker rmi <yourname>-ruby:<ruby_version>
```


## Exercise

Create an image from your container

```
docker run -it ubuntu:16.04 bash
apt-get update
apt-get install redis-tools
docker commit <container_name> dockerws/redis-tools
docker run dockerws/redis-tools redis-cli -h 192.168.20.13 info
docker run dockerws/redis-tools redis-cli -h 192.168.20.13 GET DOCKERWS
```
