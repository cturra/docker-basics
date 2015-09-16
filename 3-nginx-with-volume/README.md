About this example
------------------
This example Dockerfile will build a docker container with nginx installed and running. 
Additionally, we're shipping a customer sites-available/default configuration file. Once
up and running, you will have a default "Welcome to nginx on Debian!" page with a custom
header: `X-Docker-Basics: DOCKER`

Finally, we're including a custom "document" root directory which contains our web
application. When we run the container, we will mount this volume within the container.


Building the container
----------------------
The following Docker build command creates the container image:
```
 $ docker build -t nginx:with-volume .
```

Running the container
---------------------
The following Docker run command will get the container running with a published port and mounted
volumes in place:
```
 $ docker run --name nginx -p 8080:80 \
   -v <PATH>/docker-basics/3-nginx-with-volume/html:/usr/local/html:ro \
   -v <PATH>/docker-basics/3-nginx-with-volume/logs:/var/log/nginx:rw \
   -d nginx:with-volume
```
*where PATH is the location on your filesystem to this docker-basics repo.

Testing nginx
-------------
After the container is running, you should be able to connect locally over the published port.
```
 $ curl localhost:8080
 <!DOCTYPE html>
 <html>

 <head>
   <title> docker basics </title>
 </head>

 <body>
   <center>Docker Basics Example</center>
 </body>

 </html>
```
