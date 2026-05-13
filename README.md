# Simple Java Maven Application with Jenkins Pipeline

This repository contains a simple Java application built using Apache Maven. The application prints:

```bash
Hello world!
```

The project also includes unit tests and a Jenkins Pipeline example for learning Continuous Integration and Continuous Delivery (CI/CD).

---

# Project Structure

```bash
.
├── src/
│   ├── main/
│   │   └── java/
│   │       └── HelloWorld.java
│   │
│   └── test/
│       └── java/
│           └── HelloWorldTest.java
│
├── jenkins/
│   ├── Jenkinsfile
│   └── scripts/
│       └── deliver.sh
│
├── pom.xml
└── README.md
```

---

# About the Project

This project is designed for beginners learning:

* Java application development
* Apache Maven build automation
* Unit testing with JUnit
* Jenkins CI/CD Pipelines
* Automated testing and deployment workflows

The application is intentionally simple so that the focus remains on understanding Maven and Jenkins integration.

---

# Technologies Used

* Java
* Apache Maven
* Jenkins
* JUnit
* Shell Scripting

---

# Maven Overview

Apache Maven is a build automation and dependency management tool for Java projects.

The `pom.xml` file manages:

* Project dependencies
* Build lifecycle
* Plugins
* Test execution
* Packaging

---

# Features

## Hello World Java Application

The application outputs:

```bash
Hello world!
```

---

## Unit Testing with JUnit

The repository includes unit tests to verify application functionality.

JUnit XML reports are automatically generated after running tests and can be viewed inside Jenkins.

Generated reports location:

```bash
target/surefire-reports/
```

---

## Jenkins Pipeline

The `jenkins/Jenkinsfile` contains an example Declarative Pipeline with stages such as:

* Build
* Test
* Deliver

The pipeline automates:

1. Building the Maven project
2. Running unit tests
3. Publishing JUnit reports
4. Executing deployment scripts

---

## Delivery Script

The script:

```bash
jenkins/scripts/deliver.sh
```

is executed during the Deliver stage of the Jenkins Pipeline.

This simulates deployment or release automation.

---

# Prerequisites

Install the following before running the project:

* Java JDK 8 or higher
* Apache Maven
* Jenkins (optional for CI/CD practice)

---

# How to Run the Maven Project

## 1. Clone the Repository

```bash
git clone <repository-url>
cd simple-java-maven-app
```

---

## 2. Compile the Project

```bash
mvn clean compile
```

---

## 3. Run Unit Tests

```bash
mvn test
```

---

## 4. Package the Application

```bash
mvn package
```

This generates the `.jar` file inside:

```bash
target/
```

---

## 5. Run the Application

```bash
java -cp target/simple-java-maven-app-1.0-SNAPSHOT.jar HelloWorld
```

Expected output:

```bash
Hello world!
```

---

# Jenkins Setup

## Start Jenkins using Docker

```bash
docker run -p 8080:8080 jenkins/jenkins:lts
```

---

## Create Jenkins Pipeline

1. Open Jenkins Dashboard
2. Create a New Item
3. Select Pipeline
4. Connect your GitHub repository
5. Use Pipeline script from SCM
6. Select:

```bash
jenkins/Jenkinsfile
```

---

# Pipeline Stages

| Stage   | Description                      |
| ------- | -------------------------------- |
| Build   | Compiles the Maven project       |
| Test    | Runs JUnit test cases            |
| Reports | Generates XML test reports       |
| Deliver | Executes deployment shell script |

---

# Maven Commands Reference

| Command       | Purpose                              |
| ------------- | ------------------------------------ |
| `mvn clean`   | Removes old build files              |
| `mvn compile` | Compiles source code                 |
| `mvn test`    | Runs unit tests                      |
| `mvn package` | Creates JAR package                  |
| `mvn install` | Installs package to local repository |

---

# CI/CD Workflow

```text
Developer Pushes Code
          ↓
      Jenkins Trigger
          ↓
      Maven Build
          ↓
       Unit Tests
          ↓
   JUnit XML Reports
          ↓
      Deliver Stage
```

---

# Learning Outcomes

By completing this project, you will understand:

* Maven project structure
* Java build lifecycle
* Automated testing
* Jenkins Declarative Pipelines
* CI/CD fundamentals
* Deployment automation basics

---

# Future Improvements

Possible enhancements include:

* Docker containerization
* Kubernetes deployment
* SonarQube integration
* GitHub Actions CI/CD
* Slack notifications
* Artifact publishing

---

# License

This project is created for educational and learning purposes.
