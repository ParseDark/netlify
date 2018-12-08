---
title: mongdb搭建
date: 2018-10-14 21:45:32
tags: 数据库
---
#mongdb搭建

首先是福利：免费集群服务器（免费500M存储，三台）
https://cloud.mongodb.com/v2/5bc2d61c553855d63702205e#clusters/security/whitelist
我使用它是因为我现在想走一整个现代化的开发流程。目前在做的是一个v2ray资讯站点。目前的技术使用了：vue + webpack + express + mongodb
___
因为我用的是ubuntu 所以我的教程针对ubuntu.其余的系统只可参照。不可照搬。
___
我建议使用系统自带包管理进行安装。我试过自己下载压缩包自己解压。会比较麻烦，需要配系统变量等操作。所以我推荐按照以下步骤来做。
1. 导入包管理系统的密匙
	```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
```
2. 为MongoDB创建一个列表文件
```
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
```
3.更新所有本地安装包
```
sudo apt-get update
```
4.安装MongoDB包
默认安装最新的包
```
sudo apt-get install -y mongodb-org
```
如果有需要，那么可以指定版本下载
```
sudo apt-get install -y mongodb-org=3.6.0 mongodb-org-server=3.6.0 mongodb-org-shell=3.6.0 mongodb-org-mongos=3.6.0 mongodb-org-tools=3.6.0
```
注意，当你指定了版本号同时。使用update更新命令就会更新mongodb所以你需要执行以下命令
```
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-org-shell hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```
5.MongoDB日常操作
启动
```
sudo service mongod start
```
停止
```
sudo service mongod stop
```
重新启动MongoDB
```
sudo service mongod restart
```
6.卸载MongoDB
停止MongoDB
```
sudo service mongod stop
```
删除软件包
```
sudo apt-get purge mongodb-org*
```
删除数据目录
```
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongodb
```
















