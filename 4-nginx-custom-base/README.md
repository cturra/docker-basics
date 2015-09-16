About this example
------------------
This example Dockerfile will build a docker container with everything needed to install nginx.
That's all, it does NOT start nginx and if run will immediately exit since it has no command
to execute. It will be used as a base image to extend other docker containers.


Building the container
----------------------
The following Docker build command creates the container image:
```
 $ docker build -t nginx:base .
```
