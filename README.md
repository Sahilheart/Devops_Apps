LikeButton Application Deployment with Docker on EC2
This guide walks you through deploying the LikeButton application on an EC2 instance using Docker and Nginx.

Prerequisites
An AWS account and basic knowledge of EC2.
Git installed on your machine.
Deployment Steps
Setting Up EC2:

Navigate to the AWS Management Console and launch a new EC2 instance.
Select the Ubuntu AMI from the list.
Choose an appropriate instance type, e.g., t2.micro if you are using the AWS Free Tier.
Configuring the Security Group:

In the instance creation wizard, when you reach the "Configure Security Group" step, create a new security group or modify an existing one.
Add the following rules:
SSH: Port 22 - Source: Your IP (or anywhere if you're sure)
HTTP: Port 80 - Source: Anywhere
Custom TCP: Port 8080 - Source: Anywhere (This is for the Apache server already running on the instance.)
Review and launch the instance.
SSH into EC2:

Using your terminal or an SSH client:


ssh -i path_to_your_private_key.pem ubuntu@ip-172-31-8-80
Install Docker on Ubuntu:


sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
Clone the Sample Application:



git clone https://github.com/Sahilheart/Devops_Apps.git
cd Devops_Apps
Build the Docker Image:

docker build -t likebutton .
Run the Application in a Docker Container:

docker run -d -p 8080:80 likebutton
Since Apache is running on port 80, the LikeButton app will be accessible on port 8080. Access the application in a browser via your EC2 instance's public IP or domain:

3.136.18.75:8080
