# ubuntu版本
## docker 安装
1.卸载旧版docker（如果是全新安装的系统，无需执行）
  sudo apt-get remove docker docker-engine docker.io

2.更新系统软件
  sudo apt-get update
  
3.安装依赖包
  sudo apt-get install \\
    apt-transport-https \\
    ca-certificates \\
    curl \\
    software-properties-common

4.添加官方密钥
  建议用下面的国内源
  curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
  以下为官方
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  

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
  
8.查看docker版本
  docker -v

## docker-compose安装(用于多个服务的启动)
采用python方式安装
1.装pip
  sudo apt-get install -y python-pip
  sudo pip install --upgrade setuptools
  sudo pip install --upgrade pip

2.安装docker-compose
  sudo pip install docker-compose
3.查看版本
  docker-compose --version
  
  
  
  
  
  
  
  
  
