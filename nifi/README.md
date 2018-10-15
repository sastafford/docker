# Apache NiFi with MarkLogic Recipe

This recipe creates an Apache NiFi docker image with the MarkLogic processors and templates preloaded.  The [*Dockerizing Nifi*](https://www.bmtrealitystudios.com/dockerising-nifi/) can be credited for this recipe.  

## Building Docker Image

To build this image, save your MarkLogic NARs and templates into the nars and templates directories.  

    docker build -t gumball/nifi:latest .

## Starting NiFi: 

    docker run --name nifi -p 9090:9090 -d -e NIFI_WEB_HTTP_PORT='9090' gumball/nifi:latest

