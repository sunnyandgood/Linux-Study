# CentOs安装googole-chrome

### 第一步、配置yum下载源：

* 在目录 /etc/yum.repos.d/ 下新建文件 google-chrome.repo, 并且在该文件中添加如下内容：

        [google-chrome]
        name=google-chrome
        baseurl=http://dl.google.com/linux/chrome/rpm/stable/$basearch
        enabled=1
        gpgcheck=1
        gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub

### 第二步、安装google chrome浏览器：

    $ sudo yum -y install google-chrome-stable --nogpgcheck
