# mysql安装

### 一、下载mysql的repo源这个安装的mysql5.7.20

     [root@localhost ~]# cd /usr/local/src/
     [root@localhost src]# wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm 
     [root@localhost src]# rpm -ivh mysql57-community-release-el7-8.noarch.rpm 
     [root@localhost src]#  yum -y install mysql-server 

（也可以指定安装目录     yum --installroot=/usr/local/mysql --releasever=/ -y install mysql-server  ）这样装环境变量配置都不用你管，装上直接启动就行。安装路径是默认的。

     一路 y     

### 二、启动mysql服务

     service mysqld restart

### 三、查看预置密码

     [root@localhost ~]# grep "password" /var/log/mysqld.log    

     [root@localhost etc]# grep "password" /var/log/mysqld.log    
     2018-07-24T14:05:23.351263Z 1 [Note] A temporary password is generated for root@localhost: XziAi*I7c3ig
     2018-07-24T14:10:16.970877Z 0 [Note] Shutting down plugin 'validate_password'
     2018-07-24T14:10:18.505160Z 0 [Note] Shutting down plugin 'sha256_password'
     2018-07-24T14:10:18.505174Z 0 [Note] Shutting down plugin 'mysql_native_password'
     2018-07-24T14:15:59.866069Z 0 [Note] Shutting down plugin 'validate_password'
     2018-07-24T14:16:01.400502Z 0 [Note] Shutting down plugin 'sha256_password'
     2018-07-24T14:16:01.400510Z 0 [Note] Shutting down plugin 'mysql_native_password'
     2018-07-24T14:42:31.077291Z 0 [Note] Shutting down plugin 'validate_password'
     2018-07-24T14:42:32.711755Z 0 [Note] Shutting down plugin 'sha256_password'
     2018-07-24T14:42:32.711769Z 0 [Note] Shutting down plugin 'mysql_native_password'
     2018-07-24T17:58:44.863037Z 1 [Note] A temporary password is generated for root@localhost: 5rjlUgXvjp&a
     2018-07-24T18:04:00.694149Z 0 [Note] Shutting down plugin 'validate_password'
     2018-07-24T18:04:01.812723Z 0 [Note] Shutting down plugin 'sha256_password'
     2018-07-24T18:04:01.812725Z 0 [Note] Shutting down plugin 'mysql_native_password'
     2018-07-25T01:12:44.549658Z 2 [Note] Access denied for user 'root'@'localhost' (using password: NO)
     2018-07-25T01:12:56.218274Z 3 [Note] Access denied for user 'root'@'localhost' (using password: NO)
     2018-07-25T01:13:04.277959Z 4 [Note] Access denied for user 'root'@'localhost' (using password: NO)
     2018-07-25T01:13:07.083001Z 5 [Note] Access denied for user 'root'@'localhost' (using password: YES)
     2018-07-25T01:23:14.976935Z 0 [Note] Shutting down plugin 'validate_password'
     2018-07-25T01:23:16.705635Z 0 [Note] Shutting down plugin 'sha256_password'
     2018-07-25T01:23:16.705643Z 0 [Note] Shutting down plugin 'mysql_native_password'

### 四、输入 mysql -u root -p   密码 进入

     [root@localhost etc]# mysql -u root -p
     mysql: [Warning] World-writable config file '/etc/my.cnf' is ignored.
     Enter password: 
     Welcome to the MySQL monitor.  Commands end with ; or \g.
     Your MySQL connection id is 4
     Server version: 5.7.22

     Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

     Oracle is a registered trademark of Oracle Corporation and/or its
     affiliates. Other names may be trademarks of their respective
     owners.

     Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

     mysql> 

### 五、重置密码(5rjlUgXvjp&a )

