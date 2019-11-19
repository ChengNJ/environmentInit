# docker-compose部署web服务
## 查看服务器的磁盘情况
dfish -h 查看外挂硬盘是否挂载到/data下，没有的话进行挂载  
## 建立数据文件夹
为了避免权限问题，手动建立文件夹  
切换到root用户执行  
```
sudo mkdir -p /data/apps/logs  
sudo mkdir -p /data/files  
sudo mkdir -p /data/files/images  
sudo mkdir -p /data/files/images/video  
sudo mkdir -p /data/kafka  
sudo mkdir -p /data/zookeeper/data  
sudo mkdir -p /data/zookeeper/datalog  
sudo mkdir -p /data/mongodb  
sudo mkdir -p /data/mysql/mysql_data  
sudo mkdir -p /data/mysql/mysql_log  
sudo mkdir -p /data/nacos/data  
sudo mkdir -p /data/nacos/logs  
sudo mkdir -p /data/neo4j/data  
sudo mkdir -p /data/nginx  
sudo mkdir -p /data/redis/redis_lib  
sudo mkdir -p /data/redis/redis_log  

sudo chown -R docker:docker /data/apps  
sudo chown -R docker:docker /data/files  
sudo chown -R docker:docker /data/kafka  
sudo chown -R docker:docker /data/zookeeper  
sudo chown -R docker:docker /data/mongodb  
sudo chown -R docker:docker /data/mysql  
sudo chown -R docker:docker /data/nacos  
sudo chown -R docker:docker /data/neo4j  
sudo chown -R docker:docker /data/nginx  
sudo chown -R docker:docker /data/redis 
```

## 新建docker-compose.yaml文件（后续从网上直接拉取）
在/home/docker
修改里面的kafka的配置 将ip改成服务器的ip，如果是给外网访问，需要配置公网ip
修改nginx 的配置,使宿机要开放的端口映射到容器的80端口 以及环境变量的配置

## 拉取镜像，构建容器
在/home/aitensor目录下使用如下命令，会开始拉取镜像
```
docker-compose pull 
```
## 添加java启动依赖包
将依赖包放到/home/aitensor/lib下
远程可使用scp进行拷贝
```
scp -P port -rf lib aitensor:ip/home/aitensor/
```
## 添加前端包
将依赖包放到/home/aitensor/apps/vue
远程可使用scp进行拷贝
```
scp -P port -rf vue aitensor:ip/home/aitensor/apps/vue
```

## 添加hosts
编辑在/etc/hosts 追加以下内容 并将ip改成宿机ip
```
192.168.1.13       mysql.aitensor.com  
192.168.1.13      mongodb.aitensor.com  
192.168.1.13      redis.aitensor.com  
192.168.1.13   kafka.aitensor.com  
192.168.1.13    regcenter.aitensor.com  
192.168.1.13    fastdfs.aitensor.com  
192.168.1.13    neo4j.aitensor.com  
```

## 用root使用docker-compose 进行启动
#切换到docker-compose的目录下
```
cd /home/aitensor   
sudo docker-compose up -d
```
即可后台启动所有配置服务

## neo4j配置
访问your ip:7474 进行修改neo4j密码
 默认是neo4j
## 调整配置
基础配置
模型配置

