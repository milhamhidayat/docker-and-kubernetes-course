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