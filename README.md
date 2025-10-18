# Internship-task3
DVWA Setup on Kali Linux

1. Environment Setup
OS: Kali Linux
Apache version: 2.4.62
PHP version: 8.4
MariaDB version: 11.4.2

Commands executed:

sudo apt update
sudo apt install apache2 php php8.2-mysql mariadb-server
sudo systemctl start apache2
sudo service mysql start

2. DVWA Installation
Directory: /var/www/html/DVWA
Git clone:
git clone https://github.com/digininja/DVWA.git

Set permissions:

sudo chown -R www-data:www-data DVWA
sudo chmod -R 755 DVWA

Config file setup:
cd DVWA/config
sudo mv config.inc.php.dist config.inc.php

3. Database Setup

Database creation:

CREATE DATABASE dvwa;
CREATE USER 'dvwa_user'@'localhost' IDENTIFIED BY 'strongpassword';
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa_user'@'localhost';
FLUSH PRIVILEGES;

MariaDB status check:

sudo systemctl status mariadb
DVWA config.inc.php updated with DB credentials.

4. Web Server Check

Apache status:
sudo systemctl status apache2
DVWA accessible via: http://localhost/DVWA/setup.php

5. Notes / Observations

DVWA folder permissions set to www-data for Apache access.
Local database credentials were excluded from GitHub for security.
DVWA setup page successfully created tables in dvwa database.
PHP and MySQL modules verified (mysqli loaded
