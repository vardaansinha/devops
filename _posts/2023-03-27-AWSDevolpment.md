---
toc: true
layout: base
description: Group Hacks
categories: [markdown, Week 20]
title: AWS Devolpment
---

by: Shivansh Goel
# AWS Devolpment

###  Setting up the Server and Cloning the Project

#### Deployment Process:
- First connect to an Ubuntu EC2 instance on AWS and then begin the system and software setup.

### Update and Upgrade  the System
- sudo apt update sudo apt upgrade
- sudo apt install docker
- sudo apt install docker-compose -y
- sudo apt install html2text
- sudo apt install python3-pip nginx
- sudo pip3 install virtualenv

###  Clone and Change Directory to project location
Clone your gitserver into a directory of your choosing
- git clone https://github.com/yourgitserver

### Making sure that the Web Service can Run
To make sure that the Web Serbice to running properly
- Run the main.py file and see if the server is able to run
If there are some errors, try running the command:
- pip install -r requirements.txt

###  Make sure that there is a Dockerifle or that it is up to Date
- Edit the Dockerfile: sudo nano Dockerfile
Make sure that it looks like something like this:


FROM docker.io/python:3.9
WORKDIR /app
# --- Update environment and install python and pip ---
RUN apt-get update && apt-get upgrade -y && \
  apt-get install -y python3 python3-pip git
# --- Copy repo you updated with clone or pull ---
COPY . /app
# --- Install project specific dependencies ---
RUN pip3 install --no-cache-dir -r requirements.txt
RUN pip3 install gunicorn
# --- Setup args to run 3 workers and run on port 8080 ---
ENV GUNICORN_CMD_ARGS="--workers=3 --bind=0.0.0.0:8080"
# --- Allow port 8080 to be accessed by system ---
EXPOSE 8080
# --- Run Web Application in production style ---
CMD [ "gunicorn", "main:app" ]


### Make sure that the docker-compose.yml is up to dagte
- Edit the docker-compose.yml file and edit the flask_port, volumes, and the image

### Start Running Docker
- sudo apt install docker
- sudo apt install docker-compose -y
- sudo docker-compose up -d
- It should complete 9 steps of procesess to confirm that it is complete

### Make sure to Verify that the Web Application is working with Docker
- docker-compose ps
Make sure you find the application that matches the application name and ports. If you can't find them that means that you did something wrong and that you should go back to finish other steps.


### Testing Localpoint
To make sure that all the previous steps are running correctly and the everything is going on the right path. You should run these commands to see if there is a success or a failure.
- curl http://localhost:8086
If there is a "Failed to connect", then that means that something is not going right and that you should look at the changes you have made in the server.
- Another command to run would be: curl http://localhost:8086 | html2text

###  Test preparation for Docker Web Application using IP for Internet Access
First make sure to install Nginx
- Run the command to make sure that Nginx is installed within the system: sudo apt install nginx
Move to /etc/nginx/sites-available whichis where the Nginx Server Configuration Files are located
- Create your own configuration in the directory with a name of your choosing (sudo nano example)
- Add these stuff to the Nginx Configuration File:
server {
    listen 80;
    listen [::]:80;
    server_name 3.233.212.71;

    location / {
        proxy_pass http://localhost:8086;
        # Simple requests
        if ($request_method ~* "(GET|POST)") {
                add_header "Access-Control-Allow-Origin"  *;
        }

        # Preflight requests
        if ($request_method = OPTIONS ) {
                add_header "Access-Control-Allow-Origin"  *;
                add_header "Access-Control-Allow-Methods" "GET, POST, OPTIONS, HEAD";
                add_header "Access-Control-Allow-Headers" "Authorization, Origin, X-Requested-With, Content-Type, Accept";
                return 200;
        }
    }
}

Make sure to edit the server_name (IP Adress), the proxy pass POrt, and the docker-compose

### Activate the NGINX Configuration
- sudo ln -s /etc/nginx/sites-available/[your config file] /etc/nginx/sites-enabled[your config file]
- sudo nginx -t
If there are errors then you must go back and repeat the steps of the NGINX configuration in the sites-available directory and see if there is anything wrong or misplaced.


### Last Steps before the Last Steps
- To Conclude the first part, make sure that the internet is now running your web application:
Go on the internet and run this: http://(your ip address)

### The Last Steps
The last Steps involve setting up the DNS Server

### Video
https://www.youtube.com/watch?v=QI67AGEeQdA

# Hacks Time

### FRQ Question Hacks (Answer with more than 2-3 full complete sentneces):

- Are there any outdated Nginx/Docker functionalities to address?




- Is there anything unclear that we need to communicate further to the students for deployment?


### Diagram
To Truly understand Nginx and why we are using it, it is imortnat to compare it to other web servers?
Compare NGINX with lighttpd in a Venn Diagram, and place the image below:



