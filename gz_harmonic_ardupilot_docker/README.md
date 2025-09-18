# Gazebo Harmonic & Ardupilot models docker container

This Docker container runs Gazebo Harmonic with Ardupilot models. This method is not recommended as Gazebo will run too slow. It's better to run it on WSL directly instead of inside a container. However, Gazebo simulator runs very well inside the container with less complex models.

## Pre-built image - Docker hub

You can pull the pre-built image:

```bash
docker pull grep007/gazebo:harmonic-ardupilot
```

## Building the Container

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t gazebo:harmonic-ardupilot .
```

## Running the Container

After building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY gazebo:harmonic-ardupilot
```

## Running Gazebo Simulator

Inside the container, you can open Gazebo using the following command:

For example:

```bash
gz sim -v4 -r zephyr_runway.sdf --render-engine ogre
```
For more models, you can refer to [Ardupilot Gazebo](https://github.com/ArduPilot/ardupilot_gazebo)

![image](https://github.com/grep265/Docker/assets/81888131/d4cfdcac-e1cc-4aa1-8848-3e4737de3bfa)
