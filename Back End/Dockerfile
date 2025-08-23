# FROM maven:3.8.5-openjdk-17 AS build
# COPY . .
# RUN mvn clean package -DskipTests
# FROM openjdk:17.0.1-jdk-slim
# COPY --from=build target/Backend-0.0.1-SNAPSHOT.jar /app.jar
# EXPOSE 8080
# ENTRYPOINT ["java", "-jar", "/app.jar"]
FROM maven:3.9.6-eclipse-temurin-17 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM eclipse-temurin:17-jdk
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]