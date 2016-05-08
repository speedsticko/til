# Docker Fundamentals

Docker uses Linux kernal functionality to containerize applications.

A Docker **container** is an "instance" of a Docker **image**. Think of images like an immutable file (list an OS image) and containers as running code starting from an image.
Images are built in layers where the base layer is the OS you want to use.

# To dploy anything in Docker
1. Create a Dockerfile with your commands on how to build your image
```
FROM tomcat:8.0.20-jre8

RUN mkdir /usr/local/tomcat/webapps/myapp

COPY /1.0-SNAPSHOT/my-app-1.0-SNAPSHOT.war /usr/local/tomcat/webapps/
```
2. Run the command to build your docker image:
```
sudo docker build -t myapp .
```
3. Run the command to run your docker container:
```
sudo docker run -d -p 8080:8080 myapp
```


Cheatsheet
```
sudo docker rm <container hash>
sudo docker rmi <imagename>

sudo docker images
sudo docker ps -a

sudo docker logs <container hash>

```

docker-compose is a tool to create a group of docker containers
