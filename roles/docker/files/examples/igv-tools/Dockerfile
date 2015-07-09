FROM ubuntu:12.04
MAINTAINER Ahmed Abullah <ahmedaabdulwahed@gmail.com>

# Install IGVTools
RUN apt-get update
RUN apt-get install -y openjdk-7-jre
ADD IGVTools /usr/bin/IGVTools
ENV PATH /usr/bin/IGVTools:$PATH
