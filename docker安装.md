ubuntu版本
1.卸载旧版docker（如果是全新安装的系统，无需执行）
  sudo apt-get remove docker docker-engine docker.io

2.更新系统软件
  sudo apt-get update
  
3.安装依赖包
  sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

4.添加官方密钥
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

5.添加仓库
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
