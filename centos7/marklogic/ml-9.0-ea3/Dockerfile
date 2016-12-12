FROM mlregistry.marklogic.com/marklogic/ml-9.0-ea3

MAINTAINER Scott Stafford <scott.stafford@marklogic.com>

# If you want vim for local debugging
RUN yum -y install vim

# Start MarkLogic
RUN init-marklogic

# Expose MarkLogic Server ports
# Also expose any ports your own MarkLogic App Servers use such as
# HTTP, REST and XDBC App Servers for your applications
EXPOSE 7997 7998 7999 8000 8001 8002 8200 8201

WORKDIR /home/docker-user
ENTRYPOINT /usr/sbin/init
