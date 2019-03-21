# Create production grade workflow

## 65. Creating the dev dockerfile

To ruse Dockerfile.dev file

```sh
docker build -f Dockerfile.dev .
```

## 67. Starting the container

To run :

```sh
docker run -p 3000:3000 <container id>
```

When update react js app, it will not change automatically. The reason is because it use the old snapshot image. Need to rebuild image or another solution.

## 69. Docker volumes

Docker volumes : persist data in Docker containers or share data between connntainers.

We can bind mount the volume to container as a reference. think like an usb stick. If a container is deleted, the volume will not be deleted


Docker volume act like a volume mapping, map folder inside the container to a folder outside the container.

To add volume :

```sh
docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app <image_id>
```

-v /app/node_modules : use node_modules folder inside container, don't map with anything in local
-v $(pwd):/app : map $(pwd) (folder frontend yang ada di local) ke folder /app yang ada di container. Jadi folder /app akan ambil referensi yang ada di folder frontend, jadi tidak perlu copy dari local ke container

Try to run :

```sh
docker run -p 3000:3000 -v $(pwd):/app <image_id>
```

It will not work, because container map to node_modules folder in local. But node_modules folder in local is not exist, that's why it wasn't working. It will overwritten node_modules folder in container will node_modules in local

## 72. Overriding dockerfile selection

build: 
      context: letak dimana file yang akan dicopy ke container