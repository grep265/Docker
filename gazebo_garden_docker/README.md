# Gazebo Garden docker container

This Docker container runs Gazebo Garden. You can run Gazebo with GUI support inside the container. 

## Building the Container

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
   docker build -t gz-garden
```

## Running the Container

After building the container, you can run it using the following command:

```bash
   docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY gz-garden
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
