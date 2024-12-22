# Altschool_exam
AltExam

Altschool Second Semester Examination Project

Documentation: Provisioning the Server, Installing the Web Server, Deploying the HTML Page, and Configuring Networking

Steps Taken to Set Up an Ubuntu Web Server with Apache

Step 1: Provisioning the Server

Logged in to AWS using my IAM user credentials.
Created a new EC2 instance named "ALTSCHOOL" and started the instance.
Downloaded the key pair for the instance and noted its location on my local machine.
Configured the security group inbound rules to allow:
Port 22 (SSH) from my IP address
Port 80 (HTTP) from anywhere
Step 2: Connecting to the Server

Opened the EC2 terminal and connected to the EC2 instance via SSH:
ssh -i "MY_EC2_KEY.pem" ubuntu@54.166.55.135
Step 3: Updating the Server

Updated and upgraded the server packages:
sudo apt update && sudo apt upgrade -y
Gained root privileges:
sudo su
Step 4: Installing the Web Server

Installed Apache2 on the Ubuntu instance:
apt install apache2 -y
Started and enabled the Apache2 service:
systemctl start apache2
systemctl enable apache2
You can also confirm by going to your AWS console, copying your public IPv4 address, and pasting it into a browser: -Make sure you change the protocol to http, else you’ll get an error. -Example URL: http://34.201.76.147
Step 5: Deploying the HTML Page

Navigated to the web server’s root directory:
cd /var/www/html
Added my custom HTML file (index.html) to the directory:
nano index.html
Saved and exited the editor to deploy the page.
Step 6: Configuring Networking

Accessed freedns.afraid.org to configure a DNS record for the server’s public IP address.
Created a free subdomain and mapped it to the EC2 instance’s public IP.
Step 7: Testing the Deployment

Accessed the website using the configured subdomain in a web browser to confirm the deployment was successful.
Tested to ensure SSL was correctly assigned to my domain. Apache was running with my custom index.html landing page. SSL was successfully installed and verified.
My web server was accessible via the custom domain at:https://web.yomi1.mooo.com
@ Omoyeni Toba Joseph / ALT/SOE/024/1259
