# General Docker Commands
 
 * [Limit a Container's Resources](https://docs.docker.com/config/containers/resource_constraints/)

# Docker Command Reference

## Push to Docker Hub

    docker push <tag>

# Portainer

[Portainer](https://portainer.io/) is an open source, lightweight management user interface which allows you to easily manage your local docker hosts or swarm clusters. 

## Deployment

    docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer -H unix:///var/run/docker.sock --no-auth --restart always

# Miscellaneous

## Start TOMCAT with WAR

    docker run -it -p 8080:8080 -v $(pwd)/demo-0.0.1-SNAPSHOT.war:/usr/local/tomcat/webapps/demo.war tomcat:8.0.33

