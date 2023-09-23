##Базовые настройки ОС Ubuntu 20.04

- sudo apt install lamp-server^
- sudo -i
- apt install phpmyadmin -y
- ln -S /usr/share/phpmyadmin/  /var/www/html/phpmyadmin
- exit
- sudo mysql
- CREATE DATABASE db_name;
- CREATE user „user_name“@“localhost“ identified by „password“;
- SELECT user, host FROM mysql.user;
- GRANT ALL PRIVILEGES ON db_name.* TO „user_name“@“localhost“;
- sudo chmod -R 777 /var/www/html/
- sudo apt install git



###Конфигурация сервера Apache

- sudo nano /etc/hosts
    >   127.0.1.1	website
- cd /etc/apache2/sites-available/
- sudo cp 000-default.conf website.conf
- sudo nano website.conf
	>   ServerName website
	>	DocumentRoot /var/www/html/website/
	>	<Directory /var/www/html>
	>	AllowOverride All
	>	<\/Directory>

- sudo a2ensite website.conf
- systemctl reload apache2
- sudo a2enmod rewrite
- systemctl restart apache2

