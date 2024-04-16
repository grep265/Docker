# Alpine docker container

This Docker container runs the alpine and ping tools. This might serve a basic tool to test docker networks.

## Pre-built image - Docker hub

You can pull the pre-built image:

```bash
docker pull grep007/alpine:ping
```

## Manual build

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t alpine:ping .
```

## Running the Container

After pulling/building the container, you can run it using the following command:

```bash
docker run -it alpine:ping
```
