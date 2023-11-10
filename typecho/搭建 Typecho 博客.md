## 前言
* 服务器：阿里云
* 操作系统：CentOS Linux release 7.9.2009 (Core)

## 一、安装 Apache
```
yum install httpd        # 安装httpd服务
systemctl start httpd    # 启动httpd服务
systemctl status httpd   # 查看httpd服务状态
systemctl enable httpd   # 设置httpd服务开机启动
```

## 二、安装 PHP
```
yum install epel-release -y
rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm

yum -y remove php*

yum -y install php72w php72w-cli php72w-fpm php72w-common php72w-devel 

yum -y install php72w php72w-cli php72w-fpm php72w-common php72w-devel php72w-embedded php72w-gd php72w-mbstring php72w-mysqlnd php72w-opcache php72w-pdo php72w-xml

systemctl enable php-fpm.service
systemctl start php-fpm.service
```

## 三、安装 MySQL
```
# 下载 MySQL 源
wget http://dev.mysql.com/get/mysql57-community-release-el7-8.noarch.rpm

# 安装源
rpm -ivh mysql57-community-release-el7-8.noarch.rpm

# 安装
yum install mysql-community-server  #安装mysql-community-server
systemctl start mysqld        # 启动mysql
systemctl status mysqld       # 查看mysql 是否启动状态
systemctl enable mysqld       # 设置mysql 开机启动

# 查看数据库初始密码
grep 'temporary password' /var/log/mysqld.log
# 使用初始密码登陆
mysql -u root -p
# 修改密码 注意密码复杂度要符合要求 可以使用密码生成器
ALTER USER root@localhost IDENTIFIED BY 'password';  # 修改root密码
```

## 四、安装 Typecho
```
wget http://typecho.org/downloads/1.1-17.10.30-release.tar.gz
tar -zxvf 1.1-17.10.30-release.tar.gz
cd build/
mv * /var/www/html/
mysql -u root -p
create database typecho; # 新建数据库名为 typecho 的数据库
```
访问 http://ip/install.php 开始安装

## 参考链接
* [CentOS7.x 搭建 LAMP 环境及 Typecho 博客](https://moluuser.com/archives/6/)
* [Linux 上搭建 Typecho](https://www.tracymc.cn/archives/719)
* [博客迁移到 Typecho](https://www.skyue.com/19092713.html)