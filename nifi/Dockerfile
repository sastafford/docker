FROM apache/nifi:latest
COPY --chown=nifi:nifi nars/*.nar /opt/nifi/nifi-1.7.1/lib/
COPY --chown=nifi:nifi templates/*.xml /opt/nifi/nifi-1.7.1/conf/templates/
EXPOSE 8080
