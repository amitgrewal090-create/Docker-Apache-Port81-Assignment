Docker Hub and Apache Deployment Assignment

Project Overview

This project demonstrates Docker image management, uploading an image to Docker Hub, pulling it on a separate AWS EC2 machine, deploying the container on port 80, and verifying Apache HTTP Server.

Technologies Used

- Docker
- Docker Hub
- AWS EC2
- Amazon Linux 2023
- Apache HTTP Server
- Nginx

Docker Hub Repository

Repository:
https://hub.docker.com/r/amitkumardevops2026/amit-devops-website-apache-backup

Image:

amitkumardevops2026/amit-devops-website-apache-backup:v1

Implementation

1. Upload Image to Docker Hub

docker tag amit-devops-website-apache-backup:v1 amitkumardevops2026/amit-devops-website-apache-backup:v1

docker push amitkumardevops2026/amit-devops-website-apache-backup:v1

2. Connect to AWS EC2

Connected to a separate Amazon Linux 2023 EC2 machine using AWS Systems Manager Session Manager.

Verify Docker:

docker --version

3. Pull Image from Docker Hub

sudo docker pull amitkumardevops2026/amit-devops-website-apache-backup:v1

4. Deploy Container on Port 80

sudo docker run -d --name intellipaat-apache-port80-ec2 -p 80:8080 amitkumardevops2026/amit-devops-website-apache-backup:v1 sh -c '/usr/sbin/httpd -DFOREGROUND & exec nginx -g "daemon off;"'

Port Mapping:

- EC2 Host Port: 80
- Container Apache Port: 8080

5. Verify Docker Container

sudo docker ps

Container status was verified as running with port mapping:
"0.0.0.0:80->8080/tcp"

6. Verify Apache HTTP Server

sudo docker exec intellipaat-apache-port80-ec2 wget -qO- http://localhost:8080

Expected output:

<title>It works! Apache httpd</title>
<p>It works!</p>

7. Browser Verification

Opened the EC2 Public IPv4 address in a web browser:

"http://YOUR-EC2-PUBLIC-IP"

The Apache welcome page displayed successfully.

Evidence Screenshots

The following screenshots document the completed practical:

1. "01-dockerhub-v1-image.png" – Docker Hub image and v1 tag.
2. "02-ec2-docker-port80.png" – EC2 Docker container and port mapping.
3. "03-apache-service-verification.png" – Apache HTTP response.
4. "04-apache-public-ip-browser.png" – Apache page accessed using EC2 Public IP.

Final Result

Status: Successfully Completed

- Docker image uploaded to Docker Hub.
- Image pulled onto a separate AWS EC2 machine.
- Container deployed successfully.
- Apache HTTP Server verified.
- Website accessed through EC2 Public IPv4 address on port 80.

Conclusion

This project demonstrates practical skills in Docker image management, Docker Hub, AWS EC2, container deployment, port mapping, Apache HTTP Server verification, and remote web application access.