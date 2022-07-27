# CodeIgniter 4 Login & Register
CodeIgniter 4 Login &amp; Register Debian 10 and Ubuntu LAMP
> 
## 1. Setup Basic
dpkg-reconfigure locales
apt-get install ntp
nano /etc/bash.bashrc
timedatectl set-timezone Asia/Jakarta
date

## 2. Setup LAMP
apt-get install apache2
apt-get install php7.4- tab tab tab
apt-get install mariadb-server
mysql_secure_instalasion
apt-get install phpmyadmin

## 3. Setup CodeIgniter 4
Download file git.
Create database name ci
Change file .env
Change connection database app/Config/Database.php
Change public/ .htaccess
<textarea>
<IfModule mod_rewrite.c>
        Options +FollowSymlinks
        RewriteEngine On
        RewriteBase /
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteCond $1 !^(index\.php|robots\.txt)
        RewriteRule ^(.*)$ index.php?/$1 [L]
</IfModule mod_rewrite.c>
</textarea>

## 4. Setup Apache2
nano /etc/apache2/sites-available/code.conf
<VirtualHost *:80>
    ServerName http://159.223.59.110
    ServerAlias www.namedomain.com
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/file/code/public
    ErrorLog /var/log/apache2/codeigniter-error_log
    CustomLog /var/log/apache2/codeigniter-access_log combined
    <Directory /var/www/file/code/public>
        Require all granted
        Options FollowSymLinks
        AllowOverride All
    </Directory>
</VirtualHost>

a2enmod rewrite
/etc/init.d/apache2 restart

## 5. Open Testing
Open browser klik link url : http://ip_atau_nama_domain .
