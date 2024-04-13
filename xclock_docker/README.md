# Xclock Apps docker container

This Docker container runs the xclock app. This might serve a basic example to start testing containers with GUI capabilities.

## Pre-built image - Docker hub

You can pull the pre-built image:

```bash
docker pull grep007/xclock:latest
```

## Manual build

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t xclock .
```

## Running the Container

After pulling/building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY xclock
```
It will automatically display the xclock app

![image](https://github.com/grep265/Docker/assets/81888131/79259ca0-7c12-4b83-90c1-cb5a0d5bcb5b)
