# MarkLogic Docker Guidelines
 
 * Make sure your virtual machine settings are for >= 8 GB
 * If running on Linux, have firewalld service running

# Docker Command Reference

## Create a docker image

1. Add the MarkLogic RPM file alongside your Dockerfile.  
2. From the directory where your Dockerfile and RPM live, type the following command: docker build -t <tag> .

## Create a data volume container

    docker create -p 7997-8020:7997-8020/tcp -p 8200-8201:8200-8201/tcp -v /data --name data-store sastafford/marklogic:8.0-6.1

## Start a MarkLogic container

### MarkLogic 9

    docker run --name=ml-9 -d -p 7997-8020:7997-8020/tcp -p 8200-8201:8200-8201/tcp -v c:/:/c sastafford/marklogic:9

### MarkLogic 8

    docker run --name=ml-8 -d -p 7997-8020:7997-8020/tcp -p 8200-8201:8200-8201/tcp -v c:/:/c sastafford/marklogic:8

### Start with a data volume container

    docker run --volumes-from data-store --name=nyc -d -p 7997-8020:7997-8020/tcp -p 8200-8201:8200-8201/tcp sastafford/marklogic:9

## Attach to running MarkLogic container
    docker exec -it ml /bin/bash

## Detatch from MarkLogic container
    CTRL-p, CTRL-q

## Push to Docker Hub
    docker push <tag>

## Start a NGINX container

    docker run --name nginx -v c:/:/c -d -p 8080:80 nginx

## Start a node container
    docker run -it --rm --name node -v c:/:/c -w /usr/src/app node:latest

    docker run --name node -v c:/:/c -d -p 8080:80 node:latest

## Start a Portainer instance

### Linux
    docker run --name portainer -d -p 9000:9000/tcp -v "/var/run/docker.sock:/var/run/docker.sock" portainer/portainer


# Mount Windows Dir to Linux
     sudo mount.cifs //HPZBOOK-2921/workspace /home/scott/workspace -o credentials=/home/scott/credentials.txt,uid=scott,gid=scott,forceuid,forcegid

# Start TOMCAT with WAR
    docker run -it -p 8080:8080 -v $(pwd)/demo-0.0.1-SNAPSHOT.war:/usr/local/tomcat/webapps/demo.war tomcat:8.0.33

[Dockerizing Nifi](https://www.bmtrealitystudios.com/dockerising-nifi/)

Starting NiFi: 

    docker run --name nifi -p 9090:9090 -d -e NIFI_WEB_HTTP_PORT='9090' apache/nifi:latest

