# Gazebo Harmonic docker container

This Docker container runs Gazebo Harmonic. You can run Gazebo with GUI support inside the container. 

## Pre-built image - Docker hub

You can pull the pre-built image:

```bash
docker pull grep007/gazebo:harmonic
```

## Building the Container

Inside the folder where you have the Dockerfile, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t gazebo:harmonic .
```

## Running the Container

After building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY gazebo:harmonic
```

## Running Gazebo Simulator

Inside the container, you can open Gazebo using the following command:

```bash
gz sim --render-engine ogre
```
or open an example

```bash
gz sim shapes.sdf --render-engine ogre
```

