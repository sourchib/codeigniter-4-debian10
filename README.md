# CodeIgniter 4 Login & Register 
CodeIgniter 4 Login &amp; Register Debian 10 and Ubuntu LAMP  <br>

Doc instalasi codeIgniter new version : https://www.codeigniter.com/

## 1. Setup Basic <br>
dpkg-reconfigure locales <br>
apt-get install ntp <br>
nano /etc/bash.bashrc <br>
timedatectl set-timezone Asia/Jakarta <br>
date <br>

## 2. Setup LAMP <br>
apt-get install apache2 <br>
apt-get install php7.4- tab tab tab <br>
apt-get install mariadb-server <br>
mysql_secure_instalasion <br>
apt-get install phpmyadmin <br>

## 3. Setup CodeIgniter 4 <br>
Download file git. <br>
Create database name ci <br>
Change file .env <br>
Change connection database app/Config/Database.php <br>
Change public/ .htaccess <br>
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
