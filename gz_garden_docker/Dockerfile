FROM ubuntu:22.04

RUN apt update && \ 
apt-get install -y lsb-release wget gnupg

RUN  wget https://packages.osrfoundation.org/gazebo.gpg -O /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
 
RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null

RUN apt update && \ 
apt-get install -y gz-garden

RUN apt install -y mesa-utils

# Cleanup
RUN apt-get clean