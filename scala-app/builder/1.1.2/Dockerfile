FROM ubuntu:16.04

MAINTAINER Toshiaki Inahata <darwin49@gmail.com>


RUN apt-get update \
        && apt-get upgrade -y \
        && apt-get install -y git curl wget unzip vim \
        && apt-get install -y openjdk-8-jre openjdk-8-jdk \
        \
        && wget -O- "https://github.com/sbt/sbt/releases/download/v1.1.2/sbt-1.1.2.tgz" | tar xzf - -C /usr/local --strip-components=1 \
        && sbt exit \
        \
        && apt-get install -y nodejs npm \
        && npm cache clean \
        && npm install n -g \
        && n 8.11.1 \
        && ln -sf /usr/local/bin/node /usr/bin/node \
        \
        && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
        && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
        && apt-get install apt-transport-https -y \
        && apt-get update \
        && apt-get install -y yarn \
        \
        && apt-get install -y python-pip python-dev \
        && pip install awscli \
        \
        && apt-get clean \
        && rm -rf /var/lib/apt/lists/*
