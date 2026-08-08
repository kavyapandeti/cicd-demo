# CI/CD Demo
# Automated CI/CD Pipeline using Jenkins

## Project Overview

This project demonstrates an automated Continuous Integration and Continuous Deployment (CI/CD) pipeline using **GitHub, Jenkins, Maven, and Java**.

The pipeline automatically starts whenever new code is pushed to the GitHub repository. Jenkins then builds the application, runs tests, and reports the build status.

## Technologies Used

* **Java** – Application development
* **Maven** – Build and dependency management
* **GitHub** – Source code management
* **Jenkins** – CI/CD automation
* **GitHub Webhook** – Automatically triggers Jenkins
* **ngrok** – Connects the GitHub webhook to locally running Jenkins

## CI/CD Workflow

```text
Developer
    ↓
Push Code to GitHub
    ↓
GitHub Webhook
    ↓
ngrok
    ↓
Jenkins
    ↓
Build
    ↓
Test
    ↓
SUCCESS
```

## Jenkins Pipeline Stages

### 1. Build

Jenkins runs:

```text
mvn clean package
```

This compiles the Java application and packages it.

### 2. Test

Jenkins runs:

```text
mvn test
```

This executes the project's tests.

## Automation

Whenever code is pushed to the `main` branch:

1. GitHub detects the push.
2. GitHub sends a webhook request.
3. ngrok forwards the request to Jenkins.
4. Jenkins automatically starts the pipeline.
5. Maven builds the project.
6. Maven runs the tests.
7. Jenkins displays the final build status.

## Project Result

The CI/CD pipeline was successfully tested with an automatic Jenkins build.

**Build #5 → Finished: SUCCESS**

This confirms that the GitHub Webhook successfully triggered Jenkins automatically.

## Repository Structure

```text
cicd-demo/
├── .mvn/
├── src/
├── .gitignore
├── .gitattributes
├── Jenkinsfile
├── mvnw
├── mvnw.cmd
└── pom.xml
```

## Conclusion

This project demonstrates how GitHub, Jenkins, and Maven can be integrated to automate the software build and testing process. It reduces manual work and provides faster feedback whenever code changes are pushed.

