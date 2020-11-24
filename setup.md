## SSH Server And Laravel

### Steps :

| # |Name|Commands| Extras |
|---|---|---|---|
| 1 | Apache | <code> sudo apt-get install apache2  |
| 2 | PHP 7.3 & Dependencies  |  <code> sudo apt install php7.3-common php7.3-mysql php7.3-xml php7.3-xmlrpc php7.3-curl php7.3-gd php7.3-imagick php7.3-cli php7.3-dev php7.3-imtl -y |
| 3 | Composer | <code> sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer |
| 4 | Laravel Test | <code> sudo composer create-project laravel/laravel test |
| 5 | Apache Config - 1 |  <code> sudo nano /etc/apache2/sites-available/laravel_config.conf | <code><VirtualHost *:80> ServerAdmin ip-of-the-server DocumentRoot /var/www/html <Directory /var/www/> Options Indexes FollowSymLinks MultiViews AllowOverride All Order allow allow from all <\/Directory> <\/VirtualHost> |
| 6 | Apache Config - 2 | <code> sudo a2ensite laravel_config.conf -> enables | <code> sudo a2dissite default_configuration_file -> disables </code> <code> sudo service apache2 reload -> used in between | 
| 7 | MySQL | <code> sudo apt-get install mysql-server | 
| 8 | Git | <code> sudo apt-get install git | 
| 9 | Application Cloning | <code> sudo git clone *://*/*/item_name.git |
| 10 | NPM | <code> sudo apt-get install npm |
| 11 | Vendor & Node_modules to laravel application | <code> sudo composer update && npm install |
| 12 | .env setup for php | DB credentials |
| 13 | index.php config | <code> sudo nano var/www/html/index.php | change the vendor & bootstrap folder to relative path | 
| 14 | Create Database |<code> CREATE USER 'username'@'localhost' IDENTIFIED BY 'userpassword';</code> <code> sudo mysql -u username -p </code> <code> CREATE DATABASE database db_name; </code> <code>  USE db_name; </code> |
| 15 | Migrate Database | <code> php artisan migrate | code should be executed inside the laravelApplication folder | 
| 16 | SSL Cerification | --- | 

### Error Handling :

 - if you get unknown authentication error in laravel application use <code> CREATE  USER 'username'@'localhost' IDENTIFIED WITH mysql_native_password BY 'userpassword'; & if user exist use ALTER instead of CREATE </code>
 - if you get Requested URL was not found on the server (443), it is caused by the wrapper code. <code> sudo nano /etc/apache2/apache.conf change Override none to Override All under <Virtual Host *80> </code>
 
 
 
