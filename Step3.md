# LAMP Stack Installation Guide

This repository provides a step-by-step guide to install the LAMP stack (Linux, Apache, MySQL, PHP) on an Ubuntu server.

## Step 3 — Installing PHP

Now that Apache is installed to serve your content and MySQL is set up to store and manage data, the next step is to install **PHP**, which processes the code to display dynamic content. You will also need:

- `php-mysql`: A PHP module that allows PHP to communicate with MySQL databases.
- `libapache2-mod-php`: A module to allow Apache to handle PHP files.

### Installation Steps

1. **Install PHP and Required Modules**:
   Run the following command to install PHP along with the necessary Apache and MySQL modules:

   ```bash
   sudo apt install php libapache2-mod-php php-mysql
Verify PHP Installation: Once the installation is complete, check the PHP version to confirm it is installed correctly:
bash
Copy code
php -v
You should see the output including the version of the PHP
At this point, your LAMP stack is completely installed and fully operational.

Linux (Ubuntu)
Apache HTTP Server
MySQL
PHP
