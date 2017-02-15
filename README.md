# MarkLogic Docker Guidelines
 
 * Make sure your virtual machine settings are for >= 8 GB

# Docker Command Reference

## Create a docker image

1. Add the MarkLogic RPM file alongside your Dockerfile.  
2. From the directory where your Dockerfile and RPM live, type the following command: docker build -t <tag> .

## Start a MarkLogic container
    docker run --name=ml -d -p 7997-8002:7997-8002/tcp -p 8200-8201:8200-8201/tcp -v c:/:/c sastafford/marklogic:latest

## Attach to running MarkLogic container
    docker exec -it ml /bin/bash

## Detatch from MarkLogic container
    CTRL-p, CTRL-q

## Push to Docker Hub
    docker push <tag>
