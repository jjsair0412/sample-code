FROM openjdk:17-jdk-slim AS build

WORKDIR /app

COPY ./gradlew /app/
COPY ./gradle /app/gradle

COPY . /app/

RUN ls -al

RUN chmod +x ./gradlew

RUN ./gradlew clean build

FROM openjdk:17-jdk-slim
WORKDIR /app

COPY --from=build /app/build/libs/*.jar /app/

RUN ls -al /app/

EXPOSE 8080

ENTRYPOINT ["java","-jar","/app.jar"]
