# centOS7 解决无法挂载NTFS格式的U盘

### 一、解决方法：需要安装ntfs-3g，自带源中没有此源，需要手动添加源：

    wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo

### 二、然后再 yum makecache

    yum makecache

### 三、最后安装

    yum install ntfs-3g
