# **Docker tutorial**

### **run - start a container**
```bash
# pull if not exists and run
$ docker run nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
b8f262c62ec6: Pull complete 
a6639d774c21: Pull complete 
22a7aa8442bf: Pull complete 
Digest: sha256:9688d0dae8812dd2437947b756393eb0779487e361aa2ffbc3a529dca61f102c
Status: Downloaded newer image for nginx:latest
```

```bash
# Run a container with the nginx:1.14-alpine image and name it webapp
$ docker run --name webapp  nginx:1.14-alpine
```

### **ps - list containers**
```bash
$ docker ps

```

```bash
$ docker ps -a

```

### **stop - stop a container**
```
$ docker stop silly_sammet
```

### **rm - remove a container**
```
$ docker rm silly_sammet
```

### **images - list images**
```
$ docker images
```

### **rmi - list images**
```
$ docker rmi nginx
```

### **pull - download an image**
```
$ docker pull nginx
```

### **append a command**
```bash
# run a docker and after that wait 5 seconds before exit
$ docker run ubuntu sleep 5
```

### **exec - execute a command**
```bash
# print the content of the etc host file
$ docker exec distracted_mcclintock cat /etc/hosts
```

### **run - attach and detach**
```bash
# run a docker conatiner in the background mode and will be back in terminal immediately while running container in background
$ docker run -d kodekloud/simple-webapp
```
```bash
# run a docker conatiner in the background mode 
$ docker attach a043d
```