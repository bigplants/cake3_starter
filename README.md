# CakePHP3 starter

## Installation

1. `vagrant up`
2. `vagrant ssh`
3. `vagrant@scotchbox:~$ cd /var/www`
4. `composer install`
5. create database  
```shell
vagrant@scotchbox:~$ mysql -uroot -proot
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 41
Server version: 5.5.46-0ubuntu0.14.04.2 (Ubuntu)

Copyright (c) 2000, 2015, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create database my_app;

```

## Configuration

Read and edit `config/app.php` and setup the 'Datasources' and any other
configuration relevant for your application.

### Database configuration
- username: root
- password: root
