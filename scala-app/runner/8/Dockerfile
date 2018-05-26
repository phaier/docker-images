FROM ubuntu:16.04

MAINTAINER Toshiaki Inahata <darwin49@gmail.com>


RUN apt-get update \
        && apt-get upgrade -y \
        && apt-get install -y openjdk-8-jre openjdk-8-jdk \
        \
        && apt-get clean \
        && rm -rf /var/lib/apt/lists/*
