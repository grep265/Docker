FROM ubuntu:22.04

ARG USER_NAME=gzsim
ARG USER_UID=1000
ARG USER_GID=1000
RUN groupadd ${USER_NAME} --gid ${USER_GID}\
    && useradd -l -m ${USER_NAME} -u ${USER_UID} -g ${USER_GID} -s /bin/bash

RUN apt update && \ 
    apt-get install -y iputils-ping && \
    apt-get install -y lsb-release wget gnupg

RUN wget https://packages.osrfoundation.org/gazebo.gpg -O /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg && \ 
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null && \ 
    apt update && \ 
    apt-get install -y gz-harmonic

#RUN apt-get -y install libgl1-mesa-glx libgl1-mesa-dri

RUN apt install -y mesa-utils

WORKDIR /home/${USER_NAME}

RUN apt install -y libgz-sim8-dev rapidjson-dev git &&\ 
    git clone https://github.com/ArduPilot/ardupilot_gazebo &&\ 
    apt-get -y install g++ build-essential &&\ 
    apt-get install iputils-ping

WORKDIR /home/${USER_NAME}/ardupilot_gazebo

ENV GZ_VERSION=harmonic

RUN mkdir build &&\
    cd build && \
    cmake .. -DCMAKE_BUILD_TYPE=RelWithDebInfo &&\ 
    make -j4

WORKDIR /home/${USER_NAME}

RUN echo 'export GZ_SIM_SYSTEM_PLUGIN_PATH=/home/gzsim/ardupilot_gazebo/build:${GZ_SIM_SYSTEM_PLUGIN_PATH}' >> ~/.bashrc &&\
    echo 'export GZ_SIM_RESOURCE_PATH=/home/gzsim/ardupilot_gazebo/models:/home/gzsim/ardupilot_gazebo/worlds:${GZ_SIM_RESOURCE_PATH}' >> ~/.bashrc

RUN . ~/.bashrc 

# Cleanup
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR /home/${USER_NAME}
CMD ["bash"]