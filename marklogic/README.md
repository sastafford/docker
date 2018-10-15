# MarkLogic Docker Image Recipe

  1. Add the MarkLogic RPM file alongside your Dockerfile in this directory.  
  2. From the directory where your Dockerfile and RPM live, type the following command.

This MarkLogic image will put all of its forest and log data under the /data directory.  This will be useful when attaching docker volumes to persist storage locally.  

<!-- comment -->

    docker build -t <tag> .

# Start single MarkLogic node

    docker run --name=ml-9 -d -p 7997:7997 -p 8000-8002:8000-8002/tcp gumball/marklogic:latest

# Start MarkLogic with a Data Volume

A MarkLogic container is ephermal.  When the container is removed from the host system, the data is lost.  To persist the data beyond the lifetime of the docker container, use a data volume.  

## Create a data volume container

    docker volume create --name marklogic-data

## Start MarkLogic with the Data

    docker run -d -v marklogic-data:/data --name=ml gumball/marklogic:latest

# Attach to running MarkLogic container

    docker exec -it ml /bin/bash

To detatch from MarkLogic container: CTRL-p, CTRL-q
