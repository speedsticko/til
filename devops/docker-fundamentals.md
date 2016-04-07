# Docker Fundamentals

Docker uses Linux kernal functionality to containerize applications.

A Docker **container** is an "instance" of a Docker **image**. Think of images like an immutable file (list an OS image) and containers as running code starting from an image.
Images are built in layers where the base layer is the OS you want to use.

Cheatsheet
```
sudo docker rm <container hash>
sudo docker rmi <imagename>

sudo docker images
sudo docker ps -a

```

docker-compose is a tool to create a group of docker containers
