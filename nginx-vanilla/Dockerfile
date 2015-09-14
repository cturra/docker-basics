FROM ubuntu:14.04

MAINTAINER chris turra <cturra@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
ENV NGINX_VERSION   1.8.0-1+trusty1

# get add-apt-respository for repo bits
RUN apt-get -qq update && \
    apt-get -yf install software-properties-common

# install nginx (latest stable)
RUN add-apt-repository --yes ppa:nginx/stable && \
    apt-get -qq update && \
    apt-get -yf install nginx=${NGINX_VERSION}

# export port 80 for nginx
EXPOSE 80

# lets get nginx running
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
