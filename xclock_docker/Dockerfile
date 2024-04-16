FROM ubuntu:22.04 as runtime

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
   apt install -y x11-apps\
   apt-get install iputils-ping

CMD /usr/bin/xclock
