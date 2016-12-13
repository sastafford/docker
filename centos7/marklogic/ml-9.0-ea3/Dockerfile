FROM centos:centos7

MAINTAINER Scott Stafford <scott.stafford@marklogic.com>

RUN yum update -y && yum -y install \
  gdb.x86_64 \
  glibc.i686 \
  redhat-lsb-core.x86_64 \
  vim

ENV MARKLOGIC_INSTALL_DIR /opt/MarkLogic
ENV MARKLOGIC_DATA_DIR /data
ENV LD_LIBRARY_PATH /opt/MarkLogic/lib:/data/lib

ENV MARKLOGIC_FSTYPE ext4
ENV MARKLOGIC_USE daemon
ENV MARKLOGIC_PID_FILE /var/run/MarkLogic.pid
ENV MARKLOGIC_MLCMD_PID_FILE /var/run/mlcmd.pid
ENV MARKLOGIC_UMASK 022
ENV PATH /usr/local/sbin:/usr/local/bin:/usr/bin:/sbin:/bin:/opt/MarkLogic/mlcmd/bin

COPY *.rpm /tmp/MarkLogic.rpm

RUN yum -y install /tmp/MarkLogic.rpm && rm /tmp/MarkLogic.rpm

EXPOSE 80 443 7997 7998 7999 8000 8001 8002 8080 8200 8201

CMD /opt/MarkLogic/bin/MarkLogic && tail -f /dev/null
