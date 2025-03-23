# URL Shortener Automation with Jenkins Pipeline on AWS

## 📌 Project Overview

This project demonstrates the automation of a **Java-based URL Shortener Application** using a **Jenkins Pipeline** and deploying it on an **AWS EC2 instance** using **Docker containers**.

The pipeline automatically builds, packages, and runs the URL Shortener application inside a Docker container on the AWS Cloud, ensuring a fully containerized CI/CD workflow.
## 🔗 Project Repository

You can find the source code for the URL Shortener project here:

[👉 URL Shortener GitHub Repo](https://github.com/Shreya3145/URL-Shortner)

---

## 🛠️ Technologies Used

- **Java 17** (Spring Boot)
- **Maven** (for dependency management)
- **Docker** (for containerization)
- **Jenkins** (for CI/CD pipeline)
- **AWS EC2** (for hosting Jenkins and running containers)
- **GitHub** (for source code management)

---

## ⚙️ Pipeline Flow

1. **Source Code Checkout** from GitHub.
2. **Build & Package** the Java application using Maven.
3. **Dockerize** the application using a Dockerfile.
4. **Run** the Docker container exposing the URL Shortener service on port **8080**.

---

## 📂 Project Structure

```
shortner/
 ├── .mvn/
 ├── src/
 │   └── main/java/com/url/shortner/models/
 │       ├── ClickEvent.java
 │       ├── UrlMapping.java
 │       └── User.java
 ├── target/
 ├── pom.xml
 ├── Dockerfile
 ├── Jenkinsfile
 └── README.md
```

---

## 🚀 Deployment Steps

### 1️⃣ AWS EC2 Setup
- Launch an EC2 instance (Amazon Linux or Ubuntu).
- Open security groups for ports **22 (SSH)**, **8080 (App)**, and **8080 (Jenkins)**.
- SSH into your EC2 instance.

### 2️⃣ Install Dependencies
```bash
sudo yum update -y
sudo yum install docker git -y
sudo systemctl start docker
sudo systemctl enable docker
```

### 3️⃣ Jenkins Installation
Install Jenkins on the EC2 instance and set it up on **http://<EC2-IP>:8080**.

### 4️⃣ Jenkins Pipeline
- Create a **Pipeline job**.
- Point to your GitHub repository.
- Use the provided `Jenkinsfile` to automate build, Dockerize, and deploy your URL Shortener app.

---

## 🎯 Access the Application
After a successful pipeline run, access your URL Shortener service on:
```
http://<EC2-IP>:8080
```

---

## ✨ Features
- End-to-End automation with Jenkins.
- Fully containerized deployment using Docker.
- Hosted on cloud infrastructure (AWS EC2).
- Easy integration with version control (GitHub).

---

## 💡 Future Improvements
- Implement URL shortening logic with analytics.
- Push Docker images to a registry (Docker Hub / ECR).
- Deploy using Kubernetes on AWS (EKS).
- Set up GitHub Webhooks for automatic Jenkins triggers.


