# Quick Start Data Hub Recipe

This Docker recipe will start a brand new instance of MarkLogic, Apache NiFi and the Data Hub QuickStart from docker images.    

To spin up these docker images, execute the following command and that's it.  

    docker-compose up -d

 * Query Console: http://localhost:8000/qconsole
 * Apache NiFi: http://localhost:8080
 * Data Hub Quick Start: http://localhost:8081

The Data Hub Quick Start is mapped to this project root directory.  Make sure to select the following directory to install Quick Start.
 https://hub.docker.com/

     /usr/src/app/data-hub

To remove these docker images execute the following command.

    docker-compose down

The MarkLogic forest information is stored in a docker volume and will persist beyond the lifetime of your MarkLogic docker container. 

# Prerequisites

 * Docker version 18.06.1-ce
 * docker-compose version 1.22.0
 * [Docker Hub account](https://hub.docker.com/)
 * Access to the MarkLogic Community Docker Hub Organization, contact either Scott Stafford or Trinh Lieu



