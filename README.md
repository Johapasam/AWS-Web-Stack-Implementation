LAMP Stack Setup on AWS EC2

This project demonstrates how to set up a LAMP (Linux, Apache, MySQL, PHP) stack on an AWS EC2 instance to serve dynamic websites. The guide covers the installation and configuration of each component, leading to a fully functional web server.

Steps Involved:

1. Launching an EC2 Instance
Launched an Ubuntu EC2 instance on AWS.
Connected to the instance via SSH and updated the package manager.
2. Installing Apache
Installed the Apache web server using apt.
Verified the installation by accessing the server’s public IP address in a browser.
3. Installing MySQL
Installed MySQL for managing relational databases.
Secured the installation using the mysql_secure_installation script.
Verified the MySQL installation by logging into the MySQL shell.
4. Installing PHP
Installed PHP along with necessary modules (php-mysql and libapache2-mod-php).
Tested the PHP installation by running a PHP info script.
5. Creating a Virtual Host
Created a custom directory /var/www/projectlamp for the website.
Configured a new Apache Virtual Host file for serving the project website.
Enabled the new Virtual Host and disabled the default one.
6. Enabling PHP as Default
Edited the Apache dir.conf file to prioritize index.php over index.html.
Reloaded Apache to apply the changes.
7. Testing PHP
Created an index.php file to confirm PHP was installed and running correctly.
