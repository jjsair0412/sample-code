FROM openjdk:17.0.1-jdk-slim
ARG JAR_FILE=/home/jenkins/agent/workspace/sqk-cloud-devopsg2x8s/sqk-pipeline/sign_in_api/build/libs/signin-0.0.1-SNAPSHOT.jar
COPY ${JAR_FILE} /app.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","/app.jar"]