# **DOCKER**
docker cheat sheet

## **INTRODUCTION**

### **What is Docker?**

**Docker** is an open source project based on Linux containers. It is a tool designed to make it easier to create, deploy, and run applications using containers. **Containers** allows you to package up an application with all of it’s libraries and other dependencies, and ship it all out as one package. Docker containers are very lightweight and fast.

<p align="center">
    <img width="650" src="https://github.com/mlaskowski17/docker/blob/master/images/docker_path.png">
</p>

**A Dockerfile** is where you write the instructions to build a Docker image. These instructions can be installing software packages, setting environment variables, paths, exposing networking ports etc.


Once the Dockerfile is set up, the `docker build` command is used to build an image from it. **Docker Images** are read-only templates that you build from a set of instructions from your Dockerfile. Images define what you want your packaged application and its dependencies to look like and what processes to run when it’s launched.

These read only templates are the building blocks of a Docker container. You can use the `docker run` command to run the image and create a container. **Docker Container** is a running instance of a Docker Image. These are basically the ready applications created from Docker Images.
Docker Images are stored in the **Docker Registry**. It can be either a user’s local repository or a public repository like a Docker Hub which allows multiple users to collaborate in building an application.



#
## **COMMANDS**

### **Installation**
`curl -sSL https://get.docker.com/ | sh`



#
## **MATERIALS**

1. [Docker cheatsheet](http://dockercheatsheet.painlessdocker.com)
2. [Docker - simply explained](https://towardsdatascience.com/ml-models-prototype-to-production-6bfe47973123)
3. []()
