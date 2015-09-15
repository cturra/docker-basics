About this example
------------------
This example Dockerfile will build a docker container with nginx installed and running. No
other configuration changes are made, so you will just get a vanilla nginx install running 
the "Welcome to nginx on Debian!" page.


Building the container
----------------------
The following Docker build command creates the container image:
```
 $ docker build -t nginx:vanilla .
```

Running the container
---------------------
The following Docker run command will get the container running with a published port in place:
```
 $ docker run --name nginx -p 8080:80 -d nginx:vanilla
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
