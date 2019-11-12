# ubuntu版本
为了加快软件的安装，需要修改apt配置，使用国内源  
这边使用阿里，也可以使用清华、中科大等  
备份原来的源：
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
更换源:
sudo rm /etc/apt/sources.list
sudo vim /etc/apt/sources.list
将以下内容复制进去，保存


>#deb包
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
##测试版源  
deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
# 源码  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
##测试版源  
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse


执行更新  sudo apt-get update  
此时可以看到已经是使用阿里的镜像源  

## docker 安装
1.卸载旧版docker（如果是全新安装的系统，无需执行）  
  >sudo apt-get remove docker docker-engine docker.io

2.更新系统软件  
  >sudo apt-get update
  
3.安装依赖包
  sudo apt-get install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

4.添加官方密钥
  建议用下面的国内源,下载会更快
  curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
  以下为官方
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  
  执行可能需要小等一会，会出现ok

5.添加仓库
   建议用下面的国内源
   sudo add-apt-repository \
   "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
   
   以下为官方
  sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
   

6.再次更新软件
  sudo apt-get update

7.安装docker
  sudo apt-get install -y docker-ce
  
  静等下载安装完成。
8.查看docker版本
  docker -v

## docker-compose安装(用于多个服务的启动)
可以使用apt安装，也采用python方式安装
apt：
sudo apt-get install -y docker-compose

python:
1.装pip
  sudo apt-get install -y python-pip
  sudo pip install --upgrade setuptools
  sudo pip install --upgrade pip

2.安装docker-compose
  sudo pip install docker-compose
  
查看版本
  docker-compose --version
  
  
  
  
  
  
  
  
  
