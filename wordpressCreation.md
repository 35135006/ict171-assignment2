# Creating a wordpress from scratch

## update system
- sudo apt update
- sudo apt upgrade -y

## apache download
-sudo apt install apache2 -y

## Installing SQL
- sudo apt install mysql-server -y
- sudo mysql_secure_installation
- Press y|Y for Yes, any other key for No: y
- Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 2
- Remove anonymous users? (Press y|Y for Yes, any other key for No) : no
- Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
- Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
- Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
- ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'YourNewPassword';
- FLUSH PRIVILEGES;
- EXIT;
- DELETE FROM mysql.user WHERE User='';
- FLUSH PRIVILEGES;

## Install PHP
- sudo apt install php libapache2-mod-php php-mysql -y
- php -v


