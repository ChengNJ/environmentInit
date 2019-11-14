## docker简介
### 容器与虚拟机
我们在理解 docker 之前，首先我们得先区分清楚两个概念，容器和虚拟机。  
可能很多朋友都用过虚拟机，而对容器这个概念比较的陌生。  
我们用的传统虚拟机如 VMware ， VisualBox 之类的需要模拟整台机器包括硬件，每台虚拟机都需要有自己的操作系统，虚拟机一旦被开启，预分配给它的资源将全部被占用。每一台虚拟机包括应用，必要的二进制和库，以及一个完整的用户操作系统。  
而容器技术是和我们的宿主机共享硬件资源及操作系统，可以实现资源的动态分配。容器包含应用和其所有的依赖包，但是与其他容器共享内核。容器在宿主机操作系统中，在用户空间以分离的进程运行。  
容器技术是实现操作系统虚拟化的一种途径，可以让您在资源受到隔离的进程中运行应用程序及其依赖关系。通过使用容器，我们可以轻松打包应用程序的代码、配置和依赖关系，将其变成容易使用的构建块，从而实现环境一致性、运营效率、开发人员生产力和版本控制等诸多目标。容器可以帮助保证应用程序快速、可靠、一致地部署，其间不受部署环境的影响。容器还赋予我们对资源更多的精细化控制能力，让我们的基础设施效率更高。  

__Docker 属于 Linux 容器的一种封装，提供简单易用的容器使用接口。__ 它是目前最流行的 Linux 容器解决方案。  
而 Linux 容器是 Linux 发展出了另一种虚拟化技术，简单来讲， Linux 容器不是模拟一个完整的操作系统，而是对进程进行隔离，相当于是在正常进程的外面套了一个保护层。对于容器里面的进程来说，它接触到的各种资源都是虚拟的，从而实现与底层系统的隔离。  
Docker 将应用程序与该程序的依赖，打包在一个文件里面。运行这个文件，就会生成一个虚拟容器。程序在这个虚拟容器里运行，就好像在真实的物理机上运行一样。有了 Docker ，就不用担心环境问题。  
总体来说， Docker 的接口相当简单，用户可以方便地创建和使用容器，把自己的应用放入容器。容器还可以进行版本管理、复制、分享、修改，就像管理普通的代码一样。  
## docker 安装
1.卸载旧版docker（如果是全新安装的系统，无需执行）新建docker用户
  >sudo apt-get remove docker docker-engine docker.io
  >adduser docker
  
  有些版本会自动让填写密码已经相关信息 如果没有 运行下面命令修改密码  
  >passwd docker
  
2.更新系统软件  
  >sudo apt-get update
  
3.安装依赖包  
> sudo apt-get install -y \\  
    apt-transport-https \\  
    ca-certificates \\  
    curl \\  
    software-properties-common  
    
4.添加官方密钥  
  建议用下面的国内源,下载会更快  
  > sudo curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
  
  以下为官方
  > sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  
  执行可能需要小等一会，会出现ok  
5.添加仓库  
   建议用下面的国内源  
   > sudo add-apt-repository \\  
   "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu \\  
   $(lsb_release -cs) \\  
   stable"
   
   以下为官方
  > sudo add-apt-repository \\  
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \\  
   $(lsb_release -cs) \\  
   stable"  
   
6.再次更新软件  
  >sudo apt-get update  

7.安装docker  
  >sudo apt-get install -y docker-ce  
  
  静等下载安装完成。  
8.查看docker版本  
  >docker -v  

## docker-compose安装(用于多个服务的启动)  
可以使用apt安装，也采用python方式安装  
apt：
>sudo apt-get install -y docker-compose

python:
1.装pip
  >sudo apt-get install -y python-pip  
  sudo pip install --upgrade setuptools  
  sudo pip install --upgrade pip  

2.安装docker-compose  
  >sudo pip install docker-compose  
  
查看版本  
  >docker-compose --version  
  
  
  
  
  
  
  
  
  
