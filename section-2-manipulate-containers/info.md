# Manipulating Containers with the Docker Client

## 13. Docker run in detail

Create and run a container from image

```sh
docker run <image name>
```

ex :
```sh
docker run hello-world
```

## 14. Overriding default command

```sh
docker run <image name> command
```

command = default command override

ex:
```sh
docker run busybox echo hi there
```

will print hi there.

Run :
```sh
docker run busybox ls
```

Will list file system snapshot. File system snapshot will be put in segment in container.

Run :
```sh
docker run hello-world ls
```

It will print error, the reason : ls command is not exist in hello-world image. But ls command is exist in busybox image.

## 15. Listing running containers

list all runnning containers

```sh
docker ps
```

run:
```sh
docker run busybox ping google.com
docker ps
```

list all containers that have been created:
```sh
docker ps --all
```

## 16. Container lifecycle

docker run = docket **create** + docker **start**

Create a container:
```sh
docker create <image name>
```
Take file system from image and put it in segmented resource in container. It will return container id


Start a container:
```sh
docker start <container id>
```
Startup the command

## 17. Restart stopped containers

```sh
docker start -a <container_id>
```

-a : will watch output from container and print it.

If a container already stopped using specific command, and try to use a new command, it will not work.

## 18. Remove stopped containers

```sh
docker system prune
```

Delete all stopped containers, cache, images

## 19. Retrieving log outputs

```sh
docker logs <container_id>
```

## 20. Stopping Containers

Stop a container:
```sh
docker stop <container id>
```
Will send a termination signal to stop process. It will not automatically stop container, because it will do some clean up first. In 10 second if it doesn't stop, it will kill the container.

Kill a container:
```sh
docker kill <container id>
```
Will automatically kill the container

## 21. Multi command containers

## 22. Execute commands in running containers

Run :
```sh
docker exec -it <container id> <command>
```

exec : run another command
-it : allow us to provide input to the container
<container id> : id of container
<command> : command to execute

Ex:
```sh
docker exec -it sdlfjl redis-cli
```

## 23. The purpose of the IT flag

-it = -i -t
-i : attach to stdin
-t : format the output