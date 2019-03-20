# Building custom images through docker server

## 27. Create docker images

There are 4 steps:
1. Create docker file (contain docker configuration)
2. Docker client
3. Docker server
4. Usable image

Dockerfile step:
1. Specify a base image
2. Run some commands to install additional programs
3. Specify a command to run on container startup

## 28. Build dockerfile

## 29. Dockerfile teardown

FROM, RUN, CMD = instruction telling docker server what to do


alpine, dll = argument to the instruction

FROM : docker image that we want to use a base

RUN : execute command while prepare some image

CMD : to run container, set the primary command

## 30. Base Image

Writing a dockerfile == given a computer with no os to install chrome

like a "os"

## 31. The build process in detail

docker build .

build = give dockerfile to build image
. = set of file and folders that we want to encapsulate

example
```sh
Step 1/3 : FROM alpine
latest: Pulling from library/alpine
8e402f1a9c57: Pull complete 
Digest: sha256:644fcb1a676b5165371437feaa922943aaf7afcfa8bfee4472f6860aad1ef2a0
Status: Downloaded newer image for alpine:latest
 ---> 5cb3aa00f899
Step 2/3 : RUN apk add --update redis
 ---> Running in ce35aa0d32f9
fetch http://dl-cdn.alpinelinux.org/alpine/v3.9/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.9/community/x86_64/APKINDEX.tar.gz
(1/1) Installing redis (4.0.12-r0)
Executing redis-4.0.12-r0.pre-install
Executing redis-4.0.12-r0.post-install
Executing busybox-1.29.3-r10.trigger
OK: 7 MiB in 15 packages
Removing intermediate container ce35aa0d32f9
 ---> 72bdc100d3d8
Step 3/3 : CMD ["redis-server"]
 ---> Running in a349ad80c5f0
Removing intermediate container a349ad80c5f0
 ---> 17c4e4edd810
Successfully built 17c4e4edd810
```

## 33. Rebuilds with cache

Everytime build, it will check cache first. If exists, it will use cache. Order of instatllation will affect in building image. Must be same as original, can't reverse

## 34. Tagging an image

Tag image so when you want to run docker, you can use tag


```sh
docker run tag
```

To tag an image:
```sh
docker build <tag> .
```

. : specifies the directory of files/foldes to use fo the build

tag convention : <dockerID>.<repo/projectname>:<latest>

example : stephengrider/redis:latest

run : docker run stephengrider/redis

## 35. Manual image generation with docker commit

1. Run in terminal to create empty container

```sh
docker run -it alpine sh
```

2. In bash, install redis


```sh
apk add--update redis
```

3. In second terminal, get list of container

```sh
docker ps
```

4. Apply command

```sh
docker commit -c 'CMD["redis-server"]' <docker_id>
```

5. Run server