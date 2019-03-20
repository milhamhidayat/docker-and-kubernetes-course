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

CMD : to run container