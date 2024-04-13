# X11 Apps docker container

This Docker container runs X11 apps. This might serve a basic example to start testing containers with GUI capabilities.

## Building the Container

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t x11 .
```

## Running the Container

After building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY x11
```
It will automatically display the xclock app

## Running other apps

You can try openning another app using the following command:

For example:

```bash
xeyes
```
For more apps that you can try inside the container, you can refer to [X11 apps](https://packages.gentoo.org/categories/x11-apps)
