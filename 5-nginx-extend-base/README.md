About this example
------------------
This example Dockerfile will build a docker container entending the nginx:base
(4-nginx-custom-base) container. Specifically, we will expose a tcp port and start
nginx.

Building the container
----------------------
The following Docker build command creates the container image:
```
 $ docker build -t nginx:extend-base .
```

Running the container
---------------------
The following Docker run command will get the container running with a published port in place:
```
 $ docker run --name nginx -p 8080:80 -d nginx:extend-base
```

Testing nginx
-------------
After the container is running, you should be able to connect locally over the published port.
```
 $ curl -I localhost:8080
 HTTP/1.1 200 OK
 Server: nginx/1.8.0
 Date: Mon, 14 Sep 2015 21:44:59 GMT
 Content-Type: text/html
 Content-Length: 867
 Last-Modified: Mon, 14 Sep 2015 21:43:51 GMT
 Connection: keep-alive
 ETag: "55f73f97-363"
 Accept-Ranges: bytes
```
