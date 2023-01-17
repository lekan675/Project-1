### Project-1 Documentation

## Step 1

**Download Updates for Ubuntu**

`sudo apt update`

![Update ubuntu](./images/apt-update.png)

**Install Apache on Ubuntu**

`sudo apt install apache2`

![Install apache](./images/install-apache.png)


**Check Apache status**

`sudo systemctl status apache2`

![Apache status](./images/status.png)

- [Install OpenSSH](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=powershell#install-openssh-for-windows)

- [OpenSSH Key Management](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)


- [Adding port 80 to the inbound rule of an EC2 instance](https://aws.amazon.com/premiumsupport/knowledge-center/connect-http-https-ec2/)


![Test Ngnix server](./images/Webserver%20on%20ubuntu.jpg)


## Step 2    


**Install Mysql**

`sudo apt install mysql-server`

![Install Mysql](./images/installing%20mysqlserver%20on%20ubuntu.jpg)


**Login to  Mysql**

`sudo mysql`

![Sign in to Mysql](./images/connecting%20to%20mysql.jpg)


**Remove insecure default security settings**

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

![Remove insecure settings](./images/set%20roort%20user's%20password.jpg)

**Start interactive script running**

`sudo mysql_secure_installation`

![Mysql secure authentication](./images/mysql_secure_authentication.jpg)

**Test log in to Mysql console**

`sudo mysql -p`

![Login to Mysql console](./images/Login%20to%20MySQL%20console.jpg)


## Step 3   


**Install PHP**

`sudo apt install php libapache2-mod-php php-mysql`

![Install 3 packages - php, php-mysql and libapache2-mod-php](./images/installing_php_libapache2-mod-php_php-mysql.jpg)

`php -v`

![Confirm PHP version](./images/php%20version%207.4.3.jpg)


## Step 4


**Creating a virtual host for your websit using Apache**

`sudo mkdir /var/www/projectlamp`
`sudo chown -R $USER:$USER /var/www/projectlamp`
`sudo vi /etc/apache2/sites-available/projectlamp.conf`
`sudo ls /etc/apache2/sites-available`
`sudo a2ensite projectlamp`
`sudo a2dissite 000-default`
`sudo apache2ctl configtest`
`sudo systemctl reload apache2`
![Virtual Host for Apache](./images/web_content_config.jpg)

![Attempt to open the website URL](./images/Test%20successful.jpg)



## Step 5


**Enable PHP on the website**

`sudo vim /etc/apache2/mods-enabled/dir.conf`

`sudo systemctl reload apache2`

`vim /var/www/projectlamp/index.php`

![Edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex](./images/php.jpg)


![Test PHP installation on the browser](./images/php%20working.jpg)



