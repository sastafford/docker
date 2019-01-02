FROM openjdk:8

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
VOLUME /usr/src/app
COPY *.war /usr/src/app/quick-start.war
EXPOSE 8080

ENV SPRING_PROFILES_ACTIVE=prod
ENV MARKLOGIC_HOST=marklogic
ENV MARKLOGIC_USERNAME=admin
ENV MARKLOGIC_PASSWORD=admin

CMD ["sh", "-c", "java -jar quick-start.war \
--spring.profiles.active=${SPRING_PROFILES_ACTIVE} \
--marklogic.host=${MARKLOGIC_HOST} \
--marklogic.username=${MARKLOGIC_USERNAME} \
--marklogic.password=${MARKLOGIC_PASSWORD}"]
