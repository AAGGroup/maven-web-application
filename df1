FROM alpine/git as clone
WORKDIR /app
RUN git clone "https://github.com/AAGGroup/maven-web-application"


FROM maven:3.5-jdk-8-alpine as build
WORKDIR /app
COPY --from=clone /app/maven-web-application /app
RUN  mvn install

FROM tomcat:8.0.20-jre8 as deploy
ENV CATALINA_HOME /usr/local/tomcat
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME
COPY --from=build /app/target/*war $CATALINA_HOME/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
