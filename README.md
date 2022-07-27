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
<p>
<IfModule mod_rewrite.c> <br>
        Options +FollowSymlinks <br>
        RewriteEngine On <br>
        RewriteBase / <br>
        RewriteCond %{REQUEST_FILENAME} !-f <br>
        RewriteCond %{REQUEST_FILENAME} !-d <br>
        RewriteCond $1 !^(index\.php|robots\.txt) <br>
        RewriteRule ^(.*)$ index.php?/$1 [L] <br>
</IfModule mod_rewrite.c> <br>
</p>

## 4. Setup Apache2
nano /etc/apache2/sites-available/code.conf
<p>
    <VirtualHost *:80> <br>
    ServerName http://159.223.59.110 <br>
    ServerAlias www.namedomain.com <br>
    ServerAdmin webmaster@localhost <br>
    DocumentRoot /var/www/file/code/public <br>
    ErrorLog /var/log/apache2/codeigniter-error_log <br>
    CustomLog /var/log/apache2/codeigniter-access_log combined <br>
    <Directory /var/www/file/code/public> <br>
        Require all granted <br>
        Options FollowSymLinks <br>
        AllowOverride All <br>
    </Directory> <br>
</VirtualHost> <br>
</p>
a2enmod rewrite <br> 
a2enssite code.conf <br>
sudo /etc/init.d/apache2 restart 

## 5. Open Testing
Open browser klik link url : http://ip_atau_nama_domain .
