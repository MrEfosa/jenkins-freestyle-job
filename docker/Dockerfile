# Dockerfile

# First stage: Build the application with Maven
FROM maven:3.8.6-jdk-11 AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the pom.xml and project source
COPY pom.xml .
COPY src ./src

# Package the application
RUN mvn clean package -DskipTests

# Second stage: Create a lightweight JRE image
FROM openjdk:11-jre-slim

# Set the working directory in the new image
WORKDIR /app

# Copy the packaged application from the builder stage
COPY --from=builder /app/target/*.jar app.jar

# Run the application
ENTRYPOINT ["java","-jar","app.jar"]
