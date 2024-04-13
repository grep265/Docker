# Xclock App docker container

This Docker container runs the xclock app. This might serve a basic example to start testing containers with GUI capabilities.

## Building the Container

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t xclock .
```

## Running the Container

After building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY xclock
```
It will automatically display the xclock app

![image](https://github.com/grep265/Docker/assets/81888131/f0385025-012f-4f16-8ffc-f6c13c97dbb3)
