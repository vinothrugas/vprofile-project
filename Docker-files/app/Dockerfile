FROM openjdk:11 AS BUILD_IMAGE

LABEL "project"="Vprofile"
LABEL "Author"="vinoth"

RUN apt update && apt install maven -y
RUN git clone https://github.com/vinothrugas/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]