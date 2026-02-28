# Jenkins Freestyle Job CI/CD

## Project Overview

This project demonstrates the use of Jenkins Freestyle Job for Continuous Integration and Continuous Deployment (CI/CD) using Docker, Maven, and DigitalOcean for infrastructure management.

### Key Components:
- **Jenkins:** An open-source automation server that helps automate the parts of software development related to building, testing, and deploying.
- **Docker:** A platform designed to make it easier to create, deploy, and run applications by using containers.
- **Maven:** A build automation tool primarily used for Java projects.
- **DigitalOcean:** A cloud infrastructure provider allowing developers to deploy, manage, and scale applications easily.

### Project Structure:
- `Dockerfile`: Contains instructions for creating a Docker image for the application.
- `Jenkinsfile`: Defines the pipeline for CI/CD in Jenkins.
- `pom.xml`: Maven configuration file that contains project dependencies and configurations.
- Source code directory: Contains the application source code.

### Getting Started:
1. Clone the repository:
   ```bash
   git clone https://github.com/MrEfosa/jenkins-freestyle-job.git
   ```
2. Build the Docker image from the Dockerfile:
   ```bash
   docker build -t my-app .
   ```
3. Run the Jenkins server using Docker:
   ```bash
   docker run -d -p 8080:8080 jenkins/jenkins:lts
   ```
4. Create a Freestyle job in Jenkins and link it to the GitHub repository.
5. Configure the Maven build step and build the project.
6. Deploy to DigitalOcean using the deployed artifacts.

### Conclusion:
This project serves as a reference for setting up a CI/CD pipeline using Jenkins Freestyle Job and showcases the integration of important tools such as Docker, Maven, and cloud infrastructure on DigitalOcean.