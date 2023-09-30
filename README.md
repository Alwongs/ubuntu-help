## Базовые настройки ОС Ubuntu 20.04

- sudo -i
- apt install lamp-server^ phpmyadmin
- ln -s /usr/share/phpmyadmin/  /var/www/html/phpmyadmin
- mysql
- CREATE DATABASE db_name;
- CREATE user „user_name“@“localhost“ identified by „password“;
- SELECT user, host FROM mysql.user;
- GRANT ALL PRIVILEGES ON db_name.* TO „user_name“@“localhost“;
- chmod -R 777 /var/www/html/
- apt install git
- exit


### Конфигурация сервера Apache

- sudo -i
- nano /etc/hosts  
    >```127.0.1.1	website```
- cd /etc/apache2/sites-available/
- cp 000-default.conf website.conf
- nano website.conf  

	>```ServerName website```  
	>```DocumentRoot /var/www/html/website/```  
	>```<Directory /var/www/html>```  
	>```   AllowOverride All```  
	>```</Directory>```


- a2ensite website.conf
- systemctl reload apache2
- a2enmod rewrite
- systemctl restart apache2
- exit
