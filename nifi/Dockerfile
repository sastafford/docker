FROM apache/nifi:1.8.0
COPY --chown=nifi:nifi drivers/*.jar /lib/
COPY --chown=nifi:nifi nars/*.nar /opt/nifi/nifi-current/lib/
COPY --chown=nifi:nifi templates/*.xml /opt/nifi/nifi-current/conf/templates/
EXPOSE 8080
