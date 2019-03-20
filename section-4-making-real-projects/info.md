# Making real projects with docker

# 42. Copying build files

COPY <path to folder> <place to copy stuff>

path to folder: path to folder to copy from on *your machine* relative to build context
place to copy stuff: place to copy stuff to inside *the container*

# 43. Container port mapping

```sh
docker run -p <port from local>:<destination port> <image name>
```

port from local : port accessed by user
destination port : port in container

# Specifying a workind directory

```sh
WORKDIR <path> 
```

path : any following command will be executed relative to this path in the container

example: /usr/app