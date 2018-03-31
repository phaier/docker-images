FROM ubuntu:16.04

MAINTAINER Toshiaki Inahata <darwin49@gmail.com>


#
# Set UP Ubuntu
RUN apt-get update && apt-get upgrade -y && apt-get install -y git curl wget unzip vim
# && apt-get clean


#
# Install Java 8
RUN apt-get install -y openjdk-8-jre openjdk-8-jdk


#
# Install SBT
RUN wget -O- "https://github.com/sbt/sbt/releases/download/v1.1.2/sbt-1.1.2.tgz" \
    |  tar xzf - -C /usr/local --strip-components=1 \
    && sbt exit


#
# Install Node.js
RUN apt-get install -y nodejs npm
RUN npm cache clean
RUN npm install n -g
RUN n 8.11.1
RUN ln -sf /usr/local/bin/node /usr/bin/node


#
# Install yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get install apt-transport-https -y
RUN apt-get update && apt-get install -y yarn


#
# Set UP AWS CLI
RUN apt-get install -y python-pip python-dev
RUN pip install awscli
