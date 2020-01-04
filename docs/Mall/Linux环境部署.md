# mall 在Linux环境下部署

>本文主要以图文的形式讲解mall在Linux环境下的部署，涉及在Docker容器中安装Mysql、Redis、Nginx、RabbitMQ、Elasticsearch、Mongodb，以及SpringBoot应用部署，基于CenterOS7.6。

## Docker环境安装

- 安装yum-utils

  ~~~bash
  $ yum install -y yum-utils device-mapper-persistent-data lvm2
  ~~~

- 为yum源添加docker仓库位置

  ```bash
  $ yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  ```

- 安装docker

  ```
  yum install docker-ce
  ```

- 启动docker

  ```bash
  $ systemctl start docker
  ```

- 设置docker

  ```bash
  # 开机自启动
  $ systemctl enable docker
  ```

## mysql安装

- 安装mysql5.7镜像

  ```bash
  $ docker pull mysql:5.7
  ```

- 使用docker命令启动：

  ```bash
  docker run -p 3306:3306 --name mysql \
  -v /mydata/mysql/log:/var/log/mysql \
  -v /mydata/mysql/data:/var/lib/mysql \
  -v /mydata/mysql/conf:/etc/mysql \
  -e MYSQL_ROOT_PASSWORD=root  \
  -d mysql:5.7
  ```

  