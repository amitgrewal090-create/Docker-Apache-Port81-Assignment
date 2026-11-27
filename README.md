# Docker Image Management and Apache Deployment

## Project Overview

This project covers the Docker practical tasks from Assignments 2 and 3, along with additional Docker Hub and AWS EC2 deployment work.

## Technologies Used

- Docker
- Docker Hub
- Ubuntu
- Apache HTTP Server
- AWS EC2
- Amazon Linux 2023
- Nginx

## Assignment 2 and Assignment 3: Docker Image and Apache Deployment

### Objectives

1. Save the Docker image created in Assignment 1.
2. Launch a new container using the saved Docker image.
3. Map host port 81 to the appropriate container port.
4. Enter the container and start the Apache2 service.
5. Verify the Apache web page in a browser.

### Implementation

The Docker image created during Assignment 1 was saved and reused to launch a new container.

The container was configured to make the Apache service accessible through host port 81. Apache2 was started inside the container.

### Browser Verification

Open the following address in a browser:

http://localhost:81

The Apache web page should be displayed when the container and Apache service are running.

Note: The exact image name, container name, and container port should match the practical commands and screenshots.

## Additional Practical Work: Docker Hub and AWS EC2 Deployment

### Docker Hub Repository

https://hub.docker.com/r/amitkumardevops2026/amit-devops-website-apache-backup

Docker Image:

amitkumardevops2026/amit-devops-website-apache-backup:v1

### 1. Upload Image to Docker Hub

    docker tag amit-devops-website-apache-backup:v1 amitkumardevops2026/amit-devops-website-apache-backup:v1

    docker push amitkumardevops2026/amit-devops-website-apache-backup:v1

### 2. Connect to AWS EC2

Connected to a separate Amazon Linux 2023 EC2 machine using AWS Systems Manager Session Manager.

Verify Docker:

    docker --version

### 3. Pull Image from Docker Hub

    sudo docker pull amitkumardevops2026/amit-devops-website-apache-backup:v1

### 4. Deploy Container on Port 80

    sudo docker run -d --name intellipaat-apache-port80-ec2 -p 80:8080 amitkumardevops2026/amit-devops-website-apache-backup:v1 sh -c '/usr/sbin/httpd -DFOREGROUND & exec nginx -g "daemon off;"'

Port Mapping:

- EC2 Host Port: 80
- Container Port: 8080

### 5. Verify Docker Container

    sudo docker ps

Container port mapping verified:

    0.0.0.0:80->8080/tcp

### 6. Verify Apache HTTP Server

    sudo docker exec intellipaat-apache-port80-ec2 wget -qO- http://localhost:8080

Expected response includes:

    <title>It works! Apache httpd</title>
    <p>It works!</p>

### 7. Browser Verification

The EC2 Public IPv4 address was opened in a browser:

    http://YOUR-EC2-PUBLIC-IP

The Apache welcome page was displayed successfully.

## Evidence Screenshots

The repository contains screenshots documenting Docker image management, EC2 container deployment, Apache response verification, and browser access.

## Final Result

The practical work demonstrates:

- Saving and reusing Docker images.
- Launching containers and configuring port mapping.
- Starting and verifying Apache HTTP Server.
- Uploading Docker images to Docker Hub.
- Pulling images onto a separate AWS EC2 machine.
- Deploying and verifying a container through the EC2 public IP.

## Conclusion

This project demonstrates practical experience with Docker image management, container deployment, Apache HTTP Server, port mapping, Docker Hub, and AWS EC2.

GitHub Webhook Test - 26 November 2026

## Jenkins Git Push Trigger Test

This change verifies automatic Jenkins pipeline triggering on develop branch push.

Testing Jenkins webhook after reconnecting ngrok.

Testing automatic Jenkins trigger - Assignment 2.
