# environment-installation-ubuntu-18.04
A process to  install a PHP's environment at Ubuntu 18.04

Run the code above below to install nginx
```
sudo apt-get install nginx
````

Run the code above below to install mysql
```sudo apt-get install mysql-server
```

The code above it's a step of secure in mysql
```
mysql_secure_installation
```

Run the code above below to install php with fpm (require to nginx), mysql (connection with mysql), mbstring(require to laravel) and xml(require to laravel)
```
sudo apt-get install php-fpm php-mysql php-mbstring php-xml
```
