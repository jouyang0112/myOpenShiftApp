# Use Red Hat Universal Base Image with JDK 17
#FROM openjdk:17-slim
# Argument to pass in the JAR_FILE
ARG JAR_FILE=target/*.jar
# Copy your JAR file into the image
#COPY ${JAR_FILE} /deployments/app.jar
# Set the default command to execute
# when creating a new container
#CMD ["java", "-jar", "/deployments/app.jar"]


# === WSL2 version for JDK ===
# Use Red Hat Universal Base Image with JDK 17
# Replaced openjdk:17-slim with registry.access.redhat.com/ubi8/openjdk-17:1.13.
# UBI images are maintained by Red Hat and are more secure, lightweight, and optimized for enterprise use.
# Compatible with WSL2 and Docker.
FROM registry.access.redhat.com/ubi8/openjdk-17:1.13
# Argument to pass in the JAR_FILE
ARG JAR_FILE=target/*.jar
# Create a directory for the application
# Sets /deployments as the working directory.
# Eliminates the need to write full paths (e.g., /deployments/app.jar becomes app.jar).
WORKDIR /deployments
# Copy your JAR file into the image
COPY ${JAR_FILE} app.jar
# Expose the default port (optional, if your app listens on a port)
# Exposes the default port (8080) your app might use (optional but good for clarity).
EXPOSE 8080
# Set the default command to execute
CMD ["java", "-jar", "app.jar"]
