# Build Stage
FROM maven:3.8.4-openjdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn clean install

# Final Stage
FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=build /app/target/employee-system-api-0.0.1-SNAPSHOT.jar /app/
EXPOSE 8080
CMD ["java", "-jar", "employee-system-api-0.0.1-SNAPSHOT.jar"]
