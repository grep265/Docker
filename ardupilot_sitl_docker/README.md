# ArduPilot SITL (Software-in-the-loop) docker container

This Docker container runs ArduPilot with SITL (software-in-the-loop). You can compile ArduPilot inside the container and simulate with GUI. 

## Clone ArduPilot repository

Clone the ArduPilot repository from GitHub:
```bash
git clone https://github.com/ArduPilot/ardupilot.git
```

## Pre-built image - Docker hub

You can pull the pre-built image:

```bash
docker pull grep007/ardupilot-sitl-gui:1.0
```

## Manual build

To build the Docker container, use the provided Dockerfile. Make sure you have Docker installed on your system. Inside the ardupilot folder, replace the Dockerfile with the one that is provided. After, run the following command:

```bash
docker build . -t ardupilot-sitl-gui:2.0
```

## Running the Container

After pulling/building the container and inside the ardupilot folder, you can run the following command:

```bash
docker run -it -v `pwd`:/ardupilot -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY ardupilot-sitl-gui /bin/bash 
```

## Running SITL

Run the following command inside the container. Replace the IP address and port with the corresponding one from your GCS. For example:

```bash
cd ardupilot/ArduPlane
sim_vehicle.py -v ArduPlane --map --console -I0 --out=udp:*GCS_IP_ADDRES*:*UDP_PORT*
```

![image](https://github.com/grep265/Docker/assets/81888131/70c1735f-5fff-4cc5-b4aa-db3bdf0142a6)

![image](https://github.com/grep265/Docker/assets/81888131/1f644a94-84c5-42a3-98de-796d5687cb7c)

![image](https://github.com/grep265/Docker/assets/81888131/fda6e606-65c7-492b-90f7-a9a41ec1582c)



## References

This file is based on the ArduPilot Dockerfile, but it was modified to allow GUI capabilities and a reduction in its size.
[ArduPilot](https://github.com/ArduPilot/ardupilot.git)
