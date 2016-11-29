# Docker CLI

* Basic docker CLI commands
* Manage containers

---

## Control Container
* Run
* List
* Daemonize
* Exec
* Start/Stop/Restart/Auto Restart
* Naming
* Logs
* Copy files

Note: run commands inside container "hostname, ifconfig, cat /etc/resolv.conf"

---

## Control Images
* List
* Search
* Pull
* Use private registry
* Tag
* Push

---

## Cleaning-up
* Remove container
* Remove image

---

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
