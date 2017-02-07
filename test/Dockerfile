FROM ubuntu
USER root
RUN apt-get update -y \
&& mkdir /vendor /root/app /root/cache \
&& apt-get install -y curl \
&& apt-get install -y vim
WORKDIR /root
COPY ./bin ./bin
ENV STACK=cedar-14
RUN ./bin/compile app cache
