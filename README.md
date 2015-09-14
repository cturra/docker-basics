Welcome
-------
This GitHub repo has a number of examples which work through some of the basics
about Docker. They are intended for instruction/learning and may be used as a
template for other containers.


Help
----
Using these examples and getting a connection refused with docker-machine?

Example:
```
$ docker ps
CONTAINER ID   IMAGE           COMMAND                  CREATED              STATUS              PORTS                  NAMES
c2896624b58f   nginx:vanilla   "/usr/sbin/nginx -g '"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp   nginx

$ curl http://localhost:8080
curl: (7) Failed to connect to localhost port 8080: Connection refused
```

It turns out that NATing may not have been with VirtualBox (hosting the Docker virtual
machine). The following `VBoxManage` command will setup the port forwarding on
interface 127.0.0.1 for tcp port 8080.
```
$ VBoxManage controlvm default natpf1 "name,tcp,127.0.0.1,8080,,8080"
```
