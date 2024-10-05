# LAMP Stack Installation Guide

This repository provides a step-by-step guide to install the LAMP stack (Linux, Apache, MySQL, PHP) on an Ubuntu server.

## Step 2 — Installing MySQL

Now that you have a web server running, you need to install a Database Management System (DBMS) to store and manage data for your site. MySQL is a popular relational database management system used within PHP environments, and we will use it in this project.

### Installation Steps

1. **Install MySQL Server**:
   Use the following command to install MySQL:

   sudo apt install mysql-server
Confirm installation by typing Y when prompted.

Log in to MySQL: After installation, log in to the MySQL console:

sudo mysql
You should see output similar to:


Welcome to the MySQL monitor.  Commands end with ; or \g.
Secure MySQL Installation: Run the security script to improve MySQL security:

sudo mysql_secure_installation
During this process:

Set a password for the MySQL root user. For example:
sql

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
Follow the prompts to configure the VALIDATE PASSWORD PLUGIN, if desired.
Respond with Y to the following security questions to strengthen your MySQL installation.
Test MySQL Login: Verify that the MySQL installation is secure by logging in:

sudo mysql -p
You will be prompted for the root password you just set.
Exit MySQL: To exit the MySQL console,
type:
sql

exit
Next Steps
Your MySQL server is now installed and secured. The next step is to install PHP, the final component in the LAMP stack.
