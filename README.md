# AltExam

Altschool Second Semester Examination Project

**Documentation**: Provisioning the Server, Installing the Web Server, 
Deploying the HTML Page, and Configuring Networking

## Steps Taken to Set Up an Ubuntu Web Server with Apache

### Step 1: Provisioning the Server

1. Logged in to AWS using my IAM user credentials.
2. Created a new EC2 instance named "ALTSCHOOL" and started the instance.
3. Downloaded the key pair for the instance and noted its location on my 
local machine.
4. Configured the security group inbound rules to allow:
   - Port 22 (SSH) from my IP address
   - Port 80 (HTTP) from anywhere

### Step 2: Connecting to the Server

1. Opened the EC2 terminal and connected to the EC2 instance via SSH:
   ```bash
   ssh -i "MY_EC2_KEY.pem" ubuntu@34.201.76.147
   ```
   
### Step 3: Updating the Server
1. Updated and upgraded the server packages:
```
sudo apt update && sudo apt upgrade -y
```
2. Gained root privileges:
```
sudo su
```

### Step 4: Installing the Web Server
1. Installed Apache2 on the Ubuntu instance:
```
apt install apache2 -y
```
2. Started and enabled the Apache2 service:
```
systemctl start apache2
systemctl enable apache2
```
3. You can also confirm by going to your AWS console, copying your public IPv4 address, and pasting it into a browser:
-Make sure you change the protocol to http, else you’ll get an error.
-Example URL: http://34.201.76.147

### Step 5: Deploying the HTML Page
1. Navigated to the web server’s root directory:
```
cd /var/www/html
```
2. Added my custom HTML file (index.html) to the directory:
```
nano index.html
```
3. Saved and exited the editor to deploy the page.
   
### Step 6: Configuring Networking
1. Accessed freedns.afraid.org to configure a DNS record for the server’s public IP address.
2. Created a free subdomain and mapped it to the EC2 instance’s public IP.
   
### Step 7: Testing the Deployment
1. Accessed the website using the configured subdomain in a web browser to confirm the deployment was successful.
2. Tested to ensure SSL was correctly assigned to my domain. Apache was running with my custom index.html landing page. SSL was successfully installed and verified.
3. My web server was accessible via the custom domain at:
https://web.yomi1.mooo.com

@ Joseph Toba Omoyeni / ALT/SOE/024/1259
   
