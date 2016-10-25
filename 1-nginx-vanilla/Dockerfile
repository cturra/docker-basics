FROM ubuntu:14.04

MAINTAINER chris turra <cturra@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

# mainline or stable
ENV NGINX_REPO    stable
ENV NGINX_VERSION 1.10.1-3

# install nginx (latest stable)
RUN echo "deb http://ppa.launchpad.net/nginx/${NGINX_REPO}/ubuntu trusty main "      > /etc/apt/sources.list.d/nginx.list \
 && echo "deb-src http://ppa.launchpad.net/nginx/${NGINX_REPO}/ubuntu trusty main " >> /etc/apt/sources.list.d/nginx.list \
 && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C300EE8C \
 && apt-get -q update                                                 \
 && apt-get -y install nginx=${NGINX_VERSION}+trusty0

# export port 80 for nginx
EXPOSE 80

# lets get nginx running
ENTRYPOINT [ "/usr/sbin/nginx", "-g", "daemon off;" ]
