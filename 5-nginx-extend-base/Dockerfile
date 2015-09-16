FROM nginx:base

MAINTAINER chris turra <cturra@gmail.com>

ENV DEBIAN_FRONTEND noninteractive

# export port 80 for nginx
EXPOSE 80

# lets get nginx running
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
