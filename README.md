# Deploying a docker image of a nodejs app 

This simple nodejs app can be used for demo purpose.

- **Pre-requisites**
- Docker installed


### Build the docker the image from the Dockerfile
```sh
docker build -t webappdemo .
```

### Make sure the image is built by running this command
```sh
docker image ls 
```

The output 
```sh
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
webappdemo          latest              cda556b7a0fb        20 seconds ago      109MB
```

### Run your docker container based on the image 
- The environnement variable ENVAPP can have 2 values "STAGING" or "PRODUCTION" (if not defined it should display "UNKNOWN ENVIRONNEMENT" on the web application home page)
- By default the port on the container is listening on port "3030" and on "80" on the host


```sh
docker run -d -e ENVAPP=STAGING -p 80:3030 webappdemo:latest
```

### Check that the container is running

```sh
docker ps
```

The output
```sh
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                  NAMES
afbb83a222cb        webappdemo:latest   "docker-entrypoint.s…"   5 seconds ago       Up 4 seconds        0.0.0.0:80->3030/tcp  
```

### Check you have access to the web application

http://server_ip_address


