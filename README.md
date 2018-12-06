# environment-installation-ubuntu-18.04
A process to  install a PHP's environment at Ubuntu 18.04

Install Nginx - see [How to configure Nginx](https://github.com/paulomendesdigital/how-to-configure-nginx)
```
sudo apt-get install nginx
````

Install mysql
```
sudo apt-get install mysql-server
```

The code above it's a step of secure in mysql
```
mysql_secure_installation
```

Install **php 7** with fpm (require to nginx), mysql (connection with mysql), mbstring(require to laravel) and xml(require to laravel)
```
sudo apt-get install php-fpm php-mysql php-mbstring php-xml
```

If you want install **php 5.6** run the codes below
```
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get install php5.6-fpm php5.6-mysql php5.6-mbstring php5.6-xml
```

Install phpMyAdmin
```
sudo apt-get install phpmyadmin
```

To configue phpMyAdmin, insert the code below in the default file at /etc/nginx/sites-available/default
```
location /phpmyadmin {
   root /usr/share/;
   index index.php index.html index.htm;
   
   location ~ ^/phpmyadmin/(.+\.php)$ {
     try_files $uri =404;
     root /usr/share/;
     # the line below must be the same of the php version. In this case is php 7.2
     fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
     fastcgi_index index.php;
     fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
     include /etc/nginx/fastcgi_params;
   }
   
   location ~* ^/phpmyadmin/(.+\.(jpg|jpeg|gif|css|png|js|ico|html|xml|txt))$ {
      root /usr/share/;
   }
}

location /phpMyAdmin {
       rewrite ^/* /phpmyadmin last;
}
```
