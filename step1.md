# Apache Installation on EC2

This repository contains the steps and commands for installing the Apache HTTP Server on an Amazon EC2 instance and configuring it to serve web pages over the internet.

## What is Apache?
Apache HTTP Server, developed by the Apache Software Foundation, is the most widely used web server software, powering 67% of all web servers globally. It is fast, reliable, secure, and highly customizable through extensions and modules. Most WordPress hosting providers use Apache, but it can coexist with other web servers like Nginx and Microsoft’s IIS.

## Prerequisites
- An Amazon EC2 instance running Ubuntu.
- SSH access to the EC2 instance.

## Installation Steps
1. **Update Package Manager**:
   ```bash
   sudo apt update
Install Apache:
bash
Copy code
sudo apt install apache2
Verify Apache is Running:
bash
Copy code
sudo systemctl status apache2
Ensure the status shows as green and running.
Configure Firewall

To allow incoming traffic to your web server, open TCP port 80 (the default HTTP port). In the AWS EC2 Security Groups, add a rule to allow inbound connections on port 80 from any IP address (0.0.0.0/0).

Testing

Test Locally
You can check if Apache is responding locally using:

bash
Copy code
curl http://localhost:80
or

bash
Copy code
curl http://127.0.0.1:80
Test Externally
To test if Apache is accessible from the internet, open a web browser and navigate to:

vbnet
Copy code
http://<Public-IP-Address>:80
To retrieve your public IP address, you can use:

bash
Copy code
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
Expected Result

If the installation was successful, you should see the "Apache Ubuntu Default Page," indicating that your web server is correctly installed and accessible.
