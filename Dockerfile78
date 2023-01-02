FROM tomcat:8.0.20-jre8
EXPOSE 8000
ADD target/maven-web-app.war maven-web-app.war
ENTRYPOINT ["java", "-war", "/waven-web-app.war"]
