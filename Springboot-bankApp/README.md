# Spring Boot BankApp with Docker

## Introduction
Welcome to the **Spring Boot BankApp** project! This application demonstrates how to build and deploy a multi-tier Spring Boot application with a MySQL database in a Docker environment. The app is designed to provide seamless banking functionality, and it's a perfect example of containerized application development.

---

## About This App
### What It Does
- **Main App**: A Spring Boot-based backend application handling banking operations.
- **MySQL Database**: A robust and reliable storage solution for user and transactional data.
- **Volumes**: Persistent storage for database data to ensure data remains intact across container restarts.
- **Networks**: A custom Docker network for smooth communication between the app and the database.

### How It Works
This app runs in a containerized environment using Docker and Docker Compose. The application operates on Docker port `8080`, and it can be mapped to a host port (e.g., `3200`) to avoid conflicts and simplify access. The setup ensures a well-organized and scalable development and deployment process.

---

## Project Structure
Here is the folder and file structure for the project:

```
SpringBootBankApp/
├── Dockerfile
├── docker-compose.yml
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           └── bankapp/
│   │   │               └── MainApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── schema.sql
├── pom.xml
├── images/
│   └── example-image.png
└── README.md
```

### Explanation of Files
- **Dockerfile**: Defines the instructions to build the Docker image for the Spring Boot application.
- **docker-compose.yml**: Configures the multi-container application setup, including the Spring Boot app, MySQL, volumes, and network.
- **src/**: Contains the source code for the Spring Boot application, including Java files and resource configurations.
- **pom.xml**: Maven configuration file for dependencies and build instructions.
- **images/**: Stores images used for documentation or presentation purposes.

---

## Components in Docker Environment

### 1. Main App
The main application is built on Spring Boot and handles all backend logic for banking operations. It includes:
- REST APIs for banking functionality.
- `application.properties` for configuration.

### 2. MySQL Database
The database stores user data and transactional records. Key details:
- Predefined schema in `schema.sql`.
- Data persists via Docker volumes.

### 3. Volumes
Volumes are configured in the `docker-compose.yml` file to ensure that database data persists across container restarts. This guarantees data integrity.

### 4. Network
A custom Docker network is created to ensure seamless communication between the Spring Boot app and the MySQL database. This isolates the application and database from external interference.

---

## How to Build and Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/SpringBootBankApp.git
   cd SpringBootBankApp
   ```

2. Build the Docker image:
   ```bash
   docker build -t springboot-bankapp .
   ```

3. Start the application using Docker Compose:
   ```bash
   docker-compose up
   ```

4. Access the application:
   - Default Docker Port: [http://localhost:8080](http://localhost:8080)
   - Host Port (if mapped): [http://localhost:3200](http://localhost:3200)

5. Stop the application:
   ```bash
   docker-compose down
   ```

---

## Notes
### **Key Features**
- Multi-tier architecture (application + database).
- Easy setup with Docker and Docker Compose.
- Persistent storage with Docker volumes.
- Scalable and isolated environment with Docker networks.

### **Advanced Deployment Options**
- Multi-stage builds for efficient image creation.
- Integration with Jenkins for CI/CD pipelines.
- Collaboration with GitHub for version control.
- Deployment on Kubernetes (K8s) for scaling and orchestration.

### Final Note
**<span style="font-size: 1.1em;">This is a multi-tier app. We can build this through Docker, Docker Compose, Docker multi-stage builds, Jenkins, Jenkins-GitHub collaboration, and even in Kubernetes (K8s).</span>**

