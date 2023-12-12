FROM openjdk:latest as build

COPY ./gradlew /app/
COPY ./gradle /app/gradle

COPY . /app/

RUN ls -al

RUN chmod +x ./gradlew

RUN ./gradlew clean build

FROM openjdk:17-jdk-slim
WORKDIR /app

COPY --from=build /app/build/libs/sign_in_api-0.0.1-SNAPSHOT.jar /app/

EXPOSE 8080

ENTRYPOINT ["java","-jar","/app.jar"]
