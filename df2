FROM tomcat:8.0.20-jre8 as deploy
ENV CATALINA_HOME /usr/local/tomcat
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME
COPY /target/*war $CATALINA_HOME/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
