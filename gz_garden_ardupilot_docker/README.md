# Gazebo Garden & Ardupilot models docker container

This Docker container runs Gazebo Garden with Ardupilot models. This method is not recommended as Gazebo will run too slow. It's better to run it on WSL directly instead of inside a container.

## Building the Container

Inside the folder where you have the docker file, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build -t gz-garden-sitl .
```

## Running the Container

After building the container, you can run it using the following command:

```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY gz-garden-sitl
```

## Running Gazebo Simulator

Inside the container, you can open Gazebo using the following command:

For example:

```bash
gz sim -v4 -r iris_runway.sdf --render-engine ogre
```
For more models, you can refer to [Ardupilot Gazebo](https://github.com/ArduPilot/ardupilot_gazebo)

![image](https://github.com/grep265/Docker/assets/81888131/1e0829a3-5380-49ac-81e8-5b9894d9ebe4)
