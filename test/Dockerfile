FROM ubuntu
USER root
RUN apt-get update -y
RUN mkdir /vendor /root/app /root/cache
RUN apt-get install -y curl
RUN apt-get install -y vim
WORKDIR /root
COPY ./bin ./bin
ENV STACK=cedar-14
RUN ./bin/compile app cache
