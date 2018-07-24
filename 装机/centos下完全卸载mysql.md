# CentOs下完全卸载mysql

### 一、yum方式安装的mysql

    1、yum remove mysql mysql-server mysql-libs compat-mysql51

    2、rm -rf /var/lib/mysql

    3、rm /etc/my.cnf

 

### 二、查看是否还有mysql软件：

    rpm -qa|grep mysql

    如果存在的话，继续删除即可。

 

### 三、rpm方式安装的mysql

* 1、查看系统中是否以rpm包安装的mysql：

        [root@localhost opt]# rpm -qa | grep -i mysql
        MySQL-server-5.6.17-1.el6.i686
        MySQL-client-5.6.17-1.el6.i686

 * 2、卸载mysql

        [root@localhost local]# rpm -e MySQL-server-5.6.17-1.el6.i686
        [root@localhost local]# rpm -e MySQL-client-5.6.17-1.el6.i686

* 3、删除mysql服务

        [root@localhost local]# chkconfig --list | grep -i mysql
        [root@localhost local]# chkconfig --del mysql

* 4、删除分散mysql文件夹

        [root@localhost local]# whereis mysql 
        或者 find / -name mysql

        [sunny@localhost etc]$ sudo find / -name mysql
        /home/sunny/.local/share/akonadi/db_data/mysql
        /home/sunny/softWare/mysql
        /etc/rc.d/init.d/mysql
        /etc/selinux/targeted/active/modules/100/mysql
        /etc/selinux/targeted/tmp/modules/100/mysql
        /root/.local/share/akonadi/db_data/mysql
        /usr/share/mysql


* 5、清空相关mysql的所有目录以及文件

        rm -rf /usr/lib/mysql
        rm -rf /usr/share/mysql
        rm -rf /usr/my.cnf
        ......

### 通过以上几步，mysql应该已经完全卸载干净了
