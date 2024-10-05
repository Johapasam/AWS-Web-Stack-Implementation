## Step 5 — Enable PHP on the Website

By default, Apache prioritizes the `index.html` file over the `index.php` file when serving content. This can be helpful for temporarily displaying a maintenance page by creating an `index.html` file. Once the maintenance is completed, you can remove or rename the `index.html` file, allowing the `index.php` file to be served as the default.

However, if you'd like PHP files to take precedence, you can change the behavior by modifying Apache's `DirectoryIndex` directive.

### 1. Edit the `dir.conf` File

To make the `index.php` file take precedence, edit the `dir.conf` file located in `/etc/apache2/mods-enabled/`:


sudo vim /etc/apache2/mods-enabled/dir.conf
In this file, find the DirectoryIndex directive, and modify it as follows:

apache

<IfModule mod_dir.c>
    DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
This change ensures that Apache will first look for an index.php file before any other file type when loading the default page.

2. Reload Apache
After making changes to the dir.conf file, reload Apache to apply the changes:

sudo systemctl reload apache2

3. Create a PHP Test Script
To confirm that Apache is correctly configured to handle PHP files, create a simple PHP test script in your web root folder.

Create the index.php file inside your website directory:

vim /var/www/projectlamp/index.php
Add the following PHP code to the file:

php

<?php
phpinfo();
?>
This script will display information about the PHP environment on your server.

4. Test PHP in Your Browser
Now, visit your server's IP address or domain name in your browser to load the index.php file:

http://<Public-IP-Address>:80

5. Cleanup
Once you've confirmed that PHP is working, it's a good idea to delete the index.php file to prevent exposing sensitive information about your server:

sudo rm /var/www/projectlamp/index.php
Conclusion

With this step, PHP is enabled and configured correctly on your Apache web server. You can now build and serve dynamic PHP-based websites using your custom virtual host.
![Final Output]()
