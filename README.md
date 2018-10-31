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

Install php with fpm (require to nginx), mysql (connection with mysql), mbstring(require to laravel) and xml(require to laravel)
```
sudo apt-get install php-fpm php-mysql php-mbstring php-xml
```
