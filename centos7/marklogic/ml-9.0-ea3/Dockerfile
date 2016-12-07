FROM patrickmcelwee/marklogic-dependencies:9.0-EA3

MAINTAINER Scott Stafford <scott.stafford@marklogic.com>

ENV ML_RPM_FILE MarkLogic-RHEL7-9.0-20160909.x86_64-EA3.rpm

# If you want vim for local debugging
RUN yum -y install vim

# Copy the MarkLogic installer to a temp directory in the Docker image being built
COPY ML_RPM_FILE /tmp/

# Install MarkLogic
RUN yum -y install /tmp/${ML_RPM_FILE}

# Expose MarkLogic Server ports
# Also expose any ports your own MarkLogic App Servers use such as
# HTTP, REST and XDBC App Servers for your applications
EXPOSE 7997 7998 7999 8000 8001 8002 8020

# Start MarkLogic from init.d script.
# Define default command (which avoids immediate shutdown)
CMD /etc/init.d/MarkLogic start && tail -f /dev/null
