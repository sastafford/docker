# MarkLogic Docker Guidelines
 
 * Make sure your virtual machine settings are for >= 8 GB

# Docker Command Reference

## Start a MarkLogic container
    docker run --name=ml -d -p 7997-8002:7997-8002/tcp -p 8200-8201:8200-8201/tcp -v c:/:/c marklogic-9ea3:latest

## Attach to running MarkLogic container
    docker exec -it ml /bin/bash

## Detatch from MarkLogic container
    CTRL-p, CTRL-q
