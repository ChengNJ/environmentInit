# environmentInit
用来进行环境初始化（其中包括 mysql nginx mongodb redis nacos kafka zookeeper）的安装步骤，此篇主要是docker化安装

## ubuntu版本
为了加快软件的安装，需要修改apt配置，使用国内源  
这边使用阿里，也可以使用清华、中科大等  
备份原来的源：  
>sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak  

更换源:  
>sudo rm /etc/apt/sources.list  
sudo vim /etc/apt/sources.list  

将以下内容复制进去，保存  
>#deb包  
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse  
##测试版源  
deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse  
#源码  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse  
#测试版源  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse  

执行更新  
>sudo apt-get update  

此时可以看到已经是使用阿里的镜像源  

[docker安装]( 初识docker.md)
