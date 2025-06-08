# Creating a wordpress from scratch

## update system
- sudo apt update
- sudo apt upgrade -y

## apache download
- sudo apt install apache2 -y

## Installing SQL
- sudo apt install mysql-server -y
- sudo mysql_secure_installation
- Press y|Y for Yes, any other key for No: y
- Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 2
- Remove anonymous users? (Press y|Y for Yes, any other key for No) : no
- Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
- Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
- Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y

- to reset password use: sudo systemctl stop mysql
- sudo mysqld_safe --skip-grant-tables &
- mysql -u root -p
- ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'YourNewPassword';
- FLUSH PRIVILEGES;
- EXIT;
- DELETE FROM mysql.user WHERE User='';
- FLUSH PRIVILEGES;

## Install PHP
- sudo apt install php libapache2-mod-php php-mysql -y
- php -v

## Create a Database for WordPress
- mysql -u root -p
- enter password
- CREATE DATABASE wordpress;
- CREATE USER 'username'@'something' IDENTIFIED BY 'insert password here';
- GRANT ALL PRIVILEGES ON wordpress.* TO 'username'@'something';
- FLUSH PRIVILEGES;
- EXIT;

## Download and Set Up WordPress
- cd /tmp
- curl -O https://wordpress.org/latest.tar.gz
- tar -xvzf latest.tar.gz
- sudo mv wordpress /var/www/html/wordpress
- sudo chown -R www-data:www-data /var/www/html/wordpress
- sudo chmod -R 755 /var/www/html/wordpress

## Configure Apache to Serve WordPress
- sudo nano /etc/apache2/sites-available/wordpress.conf
- <VirtualHost *:80>
    ServerAdmin admin@yourdomain.com
    DocumentRoot /var/www/html/wordpress
    ServerName yourdomain.com
    <Directory /var/www/html/wordpress>
        AllowOverride All
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
- sudo a2ensite wordpress
- sudo a2enmod rewrite
- sudo systemctl restart apache2




