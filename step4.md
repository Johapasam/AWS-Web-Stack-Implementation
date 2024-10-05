# LAMP Stack Installation Guide

This repository provides a step-by-step guide to install the LAMP stack (Linux, Apache, MySQL, PHP) on an Ubuntu server.

## Step 4 — Creating a Virtual Host for Your Website Using Apache

In this step, we will set up a domain called **projectlamp**, but you can replace it with any domain name of your choice.

### 1. Creating the Project Directory

By default, Apache on Ubuntu serves content from the `/var/www/html` directory. We will leave that as-is and add our own directory next to the default one.

To create the directory for **projectlamp**, run the following command:

sudo mkdir /var/www/projectlamp

2. Setting Permissions
Assign ownership of the directory to your current system user using the following command:

sudo chown -R $USER:$USER /var/www/projectlamp

3. Creating a Virtual Host Configuration File
Next, we will create a new virtual host configuration file in Apache’s sites-available directory. Use a command-line editor like vi or vim:

sudo vi /etc/apache2/sites-available/projectlamp.conf

4. Adding Configuration
In the blank file that opens, press i to enter insert mode and paste the following configuration:

apache
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

5. Saving and Exiting the File
To save and close the file:

Press the Esc key.
Type :wq (write and quit).
Press ENTER.

6. Enabling the Virtual Host
Enable the new virtual host with the following command:
sudo a2ensite projectlamp

7. Disabling the Default Virtual Host
If you're not using a custom domain, disable the default website to prevent Apache’s default configuration from overriding your virtual host:
sudo a2dissite 000-default

8. Testing for Syntax Errors
To check if the configuration file contains any syntax errors, run:

sudo apache2ctl configtest
If the configuration is correct, you will receive an OK message.

9. Reloading Apache
Reload Apache to apply the changes:

sudo systemctl reload apache2

10. Creating an index.html File
Now that your virtual host is enabled, create an index.html file in the /var/www/projectlamp directory. This will serve as a test page to confirm the virtual host is working.

sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html

11. Testing the Virtual Host
Open a web browser and go to your server's public IP address:

http://<Public-IP-Address>:80

You should see the text from the echo command in the browser, displaying the server’s hostname and public IP address.

You can also access the site by its public DNS name:
http://<Public-DNS-Name>:80

12. Removing the Test index.html File
Once you’re ready to deploy your application, replace the index.html file with an index.php file. Remember to remove or rename index.html as it takes precedence over index.php.



Your Apache virtual host is now set up and running. You can continue to develop and deploy your website from here.
