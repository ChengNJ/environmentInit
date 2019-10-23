# environmentInit
用来进行环境初始化（其中包括 mysql nginx mongodb redis nacos kafka zookeeper）的安装步骤，此篇主要是docker化安装

为了加速软件安装下载速度，这边将软件源改为国内阿里的

1.备份原来的源 
  sudo cp /etc/apt/sources.list /etc/apt/sources_init.list 
  将以前的源备份一下，以防以后可以用的。

2.更换源 
  sudo vim /etc/apt/sources.list 
  使用gedit或者vim打开文档，将下边的阿里源复制进去，然后点击保存关闭。

将阿里源地址复制进去 
deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse

3.更新 
  sudo apt-get update 
  更新软件 
  sudo apt-get upgrade

[docker安装]( https://github.com/ChengNJ/environmentInit/blob/master/docker%E5%AE%89%E8%A3%85.md)
