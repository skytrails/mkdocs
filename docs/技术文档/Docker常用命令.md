#Docker命令

- ##把宿主机目录挂载到镜像中

  ```bash
  $ docker run -it -v /home/dock:/usr/mnt comet bash
  ```

- ##启动命令

  ```bash
  $ docker stop comet
  $ docker start comet
  $ docker restart comet
  ```

- 查看容器状态

  

  ```bash
  usage:
     # docker inspect [docker名称/docker short id]
  ```

  > - ### 查看容器的各种状态

  > ```bash
  > # docker inspect pymom_managerselect_dev -f '{{.State.Status}}'
  > running
  > # docker inspect pymom_managerselect_dev -f '{{.State.Running}}'
  > true
  > # docker inspect pymom_managerselect_dev  -f '{{.State.Paused}}'
  > false
  > # docker inspect pymom_managerselect_dev  -f '{{.State.Restarting}}'
  > false
  > # docker inspect pymom_managerselect_dev  -f '{{.State.OOMKilled}}'
  > false
  > # docker inspect pymom_managerselect_dev  -f '{{.State.Dead}}'
  > false
  > # docker inspect pymom_managerselect_dev  -f '{{.State.Pid}}'
  > 135329
  > # docker inspect pymom_managerselect_dev  -f '{{.State.Health.Status}}'
  > healthy
  > ```

- ## 进入容器

    ```bash
  $ docker exec -it containerId bash
  ```

  

- ##查看镜像

  ```bash
  $ docker images
  ```

  

- ## 加载镜像

  ```bash
  $ docker load -i *.tar.gz
  ```

  

- ## 删除镜像

  ```bash
  $ docker rmi REPOSITORY:TAG
  ```

  