# ArduPilot SITL (Software-in-the-loop) docker container

This Docker container runs Ardupilot with SITL (software-in-the-loop). You can compile Ardupilot inside the container and simulate with GUI. 

## Clone ArduPilot container

Clone the Ardupilot repository from GitHub:
```bash
   git clone https://github.com/ArduPilot/ardupilot.git
```

## Building the Container

To build the Docker container, use the provided Dockerfile. Make sure you have Docker installed on your system.

Inside the ardupilot folder. Replace the Dockerfile with the one that is provided. After, run the following commnands:
```bash
   docker build . -t ardupilot-sitl
```

## Running the Container

After building the container, you can run it using the following command:

```bash
   docker run -it -v `pwd`:/ardupilot -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY sitl-ardupilot /bin/bash 
```

## Running SITL

Run the following command inside the container. Replace the IP address and port with the corresponding one from your GCS.

```bash
   sim_vehicle.py -v ArduPlane --map --console -I0 --out=udp:*GCS_IP_ADDRES*:*UDP_PORT*
```

## References

This file is based on the Ardupilot Dockerfile, but it was modified to allow GUI capabilities and a reduction in its size.
