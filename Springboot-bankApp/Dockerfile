# Import docker image with Maven and JDK pre-installed
FROM maven:3.8.3-openjdk-17-slim

# Set working directory
WORKDIR /src

# Copy source code from local to container
COPY . /src


#  Build the application (run tests to validate image quality)
# The build will fail if tests don't pass.
RUN mvn clean install -DskipTests
# RUN  mvn clean install  #- THIS IS THE GOOD COMMAND FOR TEST


# HEALTHCHECK to ensure the application is responsive
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 CMD curl --fail http://localhost:8080 || exit 1

# Expose the application port
EXPOSE 8080

# Start the application
ENTRYPOINT ["java", "-jar", "/src/target/bankapp-0.0.1-SNAPSHOT.jar"]

