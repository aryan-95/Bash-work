AWS DevOps Engineer Intern Assignment
Objective

This repository contains the documentation and source code for deploying a simple, custom HTML website on an AWS EC2 instance using an Nginx web server.
 Task 1: AWS EC2 Instance Provisioning
Steps Performed

    Launch Instance: Launched an Ubuntu 24.04 LTS EC2 instance (t2.micro free tier).

    Security Group Configuration: Created a new security group with the following inbound rules:

        SSH (Port 22): Allowed from My IP (for secure remote access).

        HTTP (Port 80): Allowed from Anywhere (0.0.0.0/0) (to allow public web traffic).

    Key Pair: Generated and downloaded a assin.pem key pair for authentication.

    Connection: Connected via terminal using SSH:
    Bash

    chmod 400  assign.pem
    aryan@ubuntu:~$ ssh -i /home/aryan/Downloads/assign.pem  ubuntu@18.234.160.192


Deliverables

    EC2 Public IP 

    EC2 Dashboard Screenshot 

 Task 2: Linux Basics & Nginx Installation

Once connected to the EC2 instance, the system environment was updated, and the Nginx web server was installed and verified.
Commands Executed
Bash

# Update system package lists
sudo apt update -y

# Install nginx web server 
sudo apt install nginx -y

# start  nginx server 
sudo systemctl status nginx


df -h        # Disk usage
free -m      # Memory usage (RAM) in MB
top -b -n 1  # Active running processes

Deliverables

    Nginx Status Screenshot: * System Resource Usage Screenshot:

Task 3: Host a Simple Website

The default Nginx landing page was replaced with a custom HTML page containing student profile details.
Custom HTML Content (index.html)
HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My EC2 Web Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 40px;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
            margin: auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
        }
        h1 {
            color: #007BFF;
        }
        p {
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Student Information</h1>
        <p><strong>Name:</strong> Aryan </p>
        <p><strong>College:</strong> Kiet Group of Institutions Ghaziabad</p>
        <p><strong>Branch:</strong> IT </p>
        <p><strong>Email:</strong> aryan.95rn@gmail.com</p>
        <p><strong>Current Date:</strong> 09 July 2026</p>
    </div>
</body>
</html>


Deployment Steps

    Created the custom index.html file.

    Moved the file to the default Nginx web root directory, overwriting the default page:
    Bash

    sudo cp index.html /var/www/html/index.html

    Restarted Nginx to apply changes:
    Bash

    sudo systemctl restart nginx

Deliverables

    Live Public URL:
    Browser View Screenshot:

Task 4: Git & GitHub Repository

This repository serves as the final submission for the assignment, archiving both the configuration process and the application source code.
Git Version Control Flow Used
Bash

# Initialize repository locally
git init

# Add files and commit changes
git add index.html README.md
git commit -m "Initial commit: Added custom HTML and README documentation"

# Link to GitHub and push
git branch -M main
git remote add origin 
git push -u origin main


Task 5:  Install docker and run Hello-world


# update the system
sudo apt upadte 

# Install docker 
sudo apt  install docker.io -y 

# Start and enable docker 
 sudo systemctl start docker 
 sudo systemctl enable docker

# Fetch hello-world latest image 
sudo docker run hello-world



