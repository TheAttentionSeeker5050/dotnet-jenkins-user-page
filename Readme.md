# .NET MVC Blazor Web Application with Jenkins CI/CD and MySQL

This repository contains the necessary configuration files for setting up a basic .NET MVC Blazor website, containerized with Docker Compose, integrated with Jenkins for Continuous Integration and Continuous Deployment (CI/CD), and using MySQL as the database.

## Overview

The Blazor web application is built with .NET MVC and is designed to run within Docker containers. Jenkins is used for automating the build and test process, ensuring that changes are integrated and validated by tests. MySQL serves as the backend database for the application.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Docker and Docker Compose
- Jenkins with Docker plugin
- .NET SDK

## Getting Started

To get the application running, follow these steps:

1. **Clone the Repository**

    Clone this repository to your local machine.

    ```bash
    git clone <repository-url>
    ```

2. **Start Jenkins**

    Navigate to the `jenkins_home` directory and run the Jenkins server:

    ```bash
    cd jenkins_home
    docker-compose up -d jenkins
    ```

    Access Jenkins on `http://localhost:8086` and complete the initial setup.

3. **Build and Run the Application**

    From the root directory, run the following command to build and run the application and MySQL database using Docker Compose:

    ```bash
    docker-compose up --build
    ```

    The application will be accessible on `http://localhost:8085`.

4. **Jenkins Pipeline**

    The `Jenkinsfile` located in the `jenkins_home` directory defines the CI/CD pipeline. It includes stages for building the application and running tests. Ensure that you configure the Jenkins pipeline to point to this `Jenkinsfile`.

## Testing the Application

Once the application is running, Jenkins will execute the pipeline defined in the `Jenkinsfile`. The tests will check if the server is running, the database connection is successful, and the application is listening on the correct port.

## Contributions

Contributions are welcome! Please create a pull request with your proposed changes.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
