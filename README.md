# Project-1
for project 1
INSTALLING APACHE AND UPDATING THE FIREWALL
To install apache server, I run command `sudo apt update` to update my server. The image below is the output generated

![Apache status](./images/status apache2.PNG)

After updating the package, I run command `sudo apt instal apache2` and the output in the image below was obtained

![Apache Instal](./images/Apache apt instal.PNG)

I ran command `sudo systemctl apache2` to check if apache2 is running as a service in ubuntu. The output displayed in the image below was obtained

![Apache systemctl](./images/Apache apt.PNG)

I tested Apache2 response to requests from internet by testing the [Apache2](https://34.237.243.178:80

![Apache2 http](./images/test result Apache HTTP server.PNG)

I used `sudo apt install mysql-server` to install MySQL DBMS

![Installmysql](./images/install mysql.PNG)

I logged on to the MYSQL console by tying `sudo mysql` got the output in the image below

![sudo mysql](./images/msqllogin.PNG)

I set up a password for the root user by using `mysql_native_password`

![mysql root user password](./images/password for mysql root cause.PNG)

I exited mysql and started running the interactive script using the command language `sudo mysql_secure_installation` 

![sudo mysql installation](./images/mysql instal.PNG)

I tested to know if I can log into mysql console by using `sdo mysql -p` command

![MysqlTest](./images/mysql test.PNG)

I installed 3 packages php, libapache2-mod-php and php-mysql using `sudo apt install php libapache2-mod-php php-mysql`

![php/php-mysql/libapache2-mod-php install](./images/Install php and php mysql.PNG)

I run the command `php -v` to confirm the php version. 

![php version](./images/php_version.PNG)

Created directory for 'ayodotun' using 'mkdir' command `sudo mkdir /var/www/ayodotun`

Also assigned ownership of the directory using `sudo chown -R $USER:$USER /var/www/ayodotun`

Created and opened a new configuration in the directory using the vi command `sudo vi /etc/apache2/sites-available/ayodotun.conf`

Pasted the bare-bones configuration in the blank file after hitting on i.

Saved and closed file. Used the ls command to show new file in the sites-available directory `sudo ls /etc/apache2/sites-available`

![sites_available_directory](./images/sites_available_directory_ayodotun.PNG)

I enabled the new virtual host using `sudo a2ensite ayodotun`

![enable_virtual_host](./images/enable_site.PNG)

Used command `sudo a2dissite 000-default` to disable default website that comes with apache

![disable_default_website](./images/disable_default_website.PNG)

Checked to know that configuration file does not contain any syntax errors using `sudo apache2ctl configtest`

![config_check](./images/config_ok.PNG)

Reloaded apache so that changes can take effect using command `sudo systemctl reload apache2`

![apache reload](./images/apache_reload.PNG)

index.html file was created in the location to facilitate test using `sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/ayodotun/index.html`

I logged on to the http://44.211.38.254:80 to know if the the apache virtual host is work.

![apache active](./images/virtual_apache_active.PNG)

Accessed website using DNS name. 

![Apache_DNS](./images/DNS_active.PNG)

I changed the directory mode using `sudo vim /etc/apache2/mods-enabled/dir.conf`

![index.php](./images/change_index.php.PNG)

To change the directory file to index.php I used command `sudo vim /etc/apache2/mods-enabled/dir.conf`
I inserted and saved the file. Also reloaded Apache2 using command `sudo systemctl reload apache2`

![php_file](./images/php_file apache_reload.PNG)

The PHP test script was also created to know if PHP is installed and configured correctly on the server. I used `vim /var/www/ayodotun/index.php`

This opened a blank file where `<?php
phpinfo();` was pasted. The file was saved.

![php_test](./images/php_test.PNG)


File was removed using the command `sudo rm /var/www/ayodotun/index.php`
![file.removed](./images/file_removed.PNG)