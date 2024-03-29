# **DOCKER**
docker cheat sheet

## **INTRODUCTION**

### **What is Docker?**

**Docker** is an open source project based on Linux containers. It is a tool designed to make it easier to create, deploy, and run applications using containers. **Containers** allows you to package up an application with all of it’s libraries and other dependencies, and ship it all out as one package. Docker containers are very lightweight and fast.

> image

**A Dockerfile** is where you write the instructions to build a Docker image. These instructions can be installing software packages, setting environment variables, paths, exposing networking ports etc.


Once the Dockerfile is set up, the `docker build` command is used to build an image from it. **Docker Images** are read-only templates that you build from a set of instructions from your Dockerfile. Images define what you want your packaged application and its dependencies to look like and what processes to run when it’s launched.

These read only templates are the building blocks of a Docker container. You can use the `docker run` command to run the image and create a container. **Docker Container** is a running instance of a Docker Image. These are basically the ready applications created from Docker Images.
Docker Images are stored in the **Docker Registry**. It can be either a user’s local repository or a public repository like a Docker Hub which allows multiple users to collaborate in building an application.



#
## **COMMANDS**

### **Installation**

#### Linux
```bash
# Uninstall old versions
sudo apt-get remove docker docker-engine docker.io containerd runc

# install docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

### **Docker Registries & Repositories**

| Description | Command |
| --- | --- |
| Login to a Registry | ```docker login localhost:8000``` |
| Logout from a registry | ```docker logout localhost:8000``` |
| Searching an Image | ```docker search nginx``` |
|Pulling an Image | ```docker pull nginx``` |
|Pulling an Image from localhost | ```docker pull eon01/nginx localhost:5000/myadmin/nginx``` |
|Pushing an Image | ```docker push eon01/nginx``` |
|Pushing an Image from localhost| ```docker push eon01/nginx localhost:5000/myadmin/nginx``` |


### **Running Containerss**

| Description | Command |
| --- | --- |
| Creating a Container | ```docker create -t -i eon01/infinite --name infinite```| 
|  Running a Container| ```docker run -it --name infinite -d eon01/infinite```| 
|  Renaming a Container| ```docker rename infinite infinity```| 
|  Removing a Container | ```docker rm infinite```| 
|  Updating a Container| ```docker update --cpu-shares 512 -m 300M infinite```| 


### **Starting and Stoping Containers**

| Description | Command |
| --- | --- |
|Starting | ```docker start nginx```|
| Stopping| ```docker stop nginx```|
|Restarting| ```docker restart nginx```|
| Pushing| ```docker pause nginx```|
|Unpaussing| ```docker unpause nginx```|
| Blocking a Container| ```docker wait nginx```|
| Sending a SIGKILL| ```docker kill nginx```|
| Connecting to an Existing Container | ```docker attach nginx```|

### **Getting Information about Containers**

| Description | Command |
| --- | --- |
| Running Containers| ```docker ps -a```|
| Containers Logs| ```docker logs infinite```|
| Inspecting Containers| ```docker inspect infinite```|
| Containers Events| ```docker events infinite```|
| Public Ports| ```docker port infinite```|
| Running processes| ```docker top infinite```|
| Container Resource Usage| ```docker stats infinite```|
| Inspecting changes to files or directories on a container’s filesystem| ```docker diff infinite```|


### **Manipulating Images**

| Description | Command |
| --- | --- |
| Listing Images | ```docker images```|
| Building Image | ```docker build .``` |
|Building from github |```docker build github.com/creack/docker-firefox```|
| Building from DockerFile | ```docker build - < Dockerfile```|
|Building from .tar.gz |```docker build - < context.tar.gz```|
| Removing and Image| ```docker rmi nginx```|
| Loading a Tarred Repository from a File| ```docker load < ubuntu.tar.gz``` |
| Loading a Tarred Repository from the Standard Input Stream| ```docker load --input ubuntu.tar``` | 
|  Save an image to a Tar Archieve|  ```docker save busybox > ubuntu.tar```| 
|  Showing the History of an Image|  ```docker history```| 
|  Creating an Image From a Container |  ``` docker commit nginx```| 
|  Tagging an Image| ```docker tag nginx eon01/nginx```| 
|  Pushing an Image| ```docker push eon01/nginx```| 

### **Cleaning Docker**

| Description | Command |
| --- | --- |
|  Removing a Running Container|  ```docker rm nginx```| 
|  Removing a Container and its Volume| ```docker rm -v nginx```| 
|  Removing all Exited Containers| ```docker rm $(docker ps -a -f status=exited -q)```|
|  Removing All Stopped Containers| ``` docker rm `docker ps -a -q` ```| 
|  Removing a Docker Image| ```docker rmi nginx```| 
|  Removing Dangling Images|```docker rmi $(docker images -f dangling=true -q)```| 
|  Removing all Images| ```docker rmi $(docker images -a -q)```|  
|  Stopping & Removing all Containers| ```docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)```| 
|  Removing Dangling Volumes| ```docker volume rm $(docker volume ls -f dangling=true -q)```| 





#
## **DOCKERFILE**


#
## **REFERENCES**

1. [Docker cheatsheet](http://dockercheatsheet.painlessdocker.com)
2. [Docker CLI cheatsheer](https://devhints.io/docker)
3. [Docker-compose cheatsheet](https://devhints.io/docker-compose)
4. [DockerFile cheatsheet](https://devhints.io/dockerfile)
5. [docker CLI & Dockerfile Cheat Sheet](https://design.jboss.org/redhatdeveloper/marketing/docker_cheatsheet/cheatsheet/images/docker_cheatsheet_r3v2.pdf)

