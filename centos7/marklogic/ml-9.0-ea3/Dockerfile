FROM centos:centos7

MAINTAINER Scott Stafford <scott.stafford@marklogic.com>

ENV ML_RPM_FILE MarkLogic-RHEL7-9.0-20160909.x86_64-EA3.rpm

# Get any CentOS updates then clear the Docker cache
RUN yum -y update && yum clean all

# Install MarkLogic dependencies
RUN yum -y install glibc.i686 gdb.x86_64 redhat-lsb.x86_64 && yum clean all

# Install the initscripts package so MarkLogic starts ok
RUN yum -y install initscripts && yum clean all

# Set the Path
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/MarkLogic/bin

# Copy the MarkLogic installer to a temp directory in the Docker image being built
COPY ML_RPM_FILE /tmp/

# Install MarkLogic
RUN yum -y install /tmp/${ML_RPM_FILE}

# Expose MarkLogic Server ports
# Also expose any ports your own MarkLogic App Servers use such as
# HTTP, REST and XDBC App Servers for your applications
EXPOSE 7997 7998 7999 8000 8001 8002

# Start MarkLogic from init.d script.
# Define default command (which avoids immediate shutdown)
CMD /etc/init.d/MarkLogic start && tail -f /dev/null
