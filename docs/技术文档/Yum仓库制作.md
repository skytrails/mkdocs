# yum仓库制作

[TOC]

## Yum本地仓库制作

[skytrails@163.com]

### CentOS7.5

---

- 装载ISO系统盘到/mnt/DVDISO 或 使用vbox的共享路径功能
- 在mnt目录上执行createrepo命令
- 备份删除/etc/yum.repo.d全部文件
- 新建以下内容文件(CentOS-DVD.repo)

```bash
  [DVDISO]
  name=DVD ISO
  baseurl=file:///mnt/   # 大爷的，这里有三个‘/’,踩过坑
  enabled=1
  gpgcheck=0
```

- 执行yum clean all
- 执行yum list验证

## http方式共享yum源

### 服务端配置

> - 安装httpd服务
>
>   ```bash
>   $ yum install -y httpd
>   ```
>
> - 关联路径
>
>   ```bash
>   $ ln -s /mnt/DVDISO /var/www/html/repos
>   ```
>
> - 配置httpd
>
>   ```shell
>   $ cat /etc/httpd/conf.d/repos.d
>    <Directory /var/www/http/repos>
>   	   Options +Indexes
>       Require all granted
>    </Directory>
>    Alias /repos /var/www/html/repos
>   ```
>
> - 路径访问权限
>
>   ```bash
>   # 为了httpd有权限访问/mnt/DVDISO
>   $ usermod -G vboxsf apache
>   ```
>
> - 重启httpd服务
>
>   ```bash
>   $ systemctl restart httpd
>   ```

### 客户端配置

> - 备份repo文件
>
> ```bash
> $ cd /etc/yum.d/ 
> $ mkdir bak
> $ mv C* bak/
> ```
>
> - 配置repo文件
>
> - ```bash
>   $ vi /etc/yum.d/httpd.repo
>   [share]
>   name=httpd.repo
>   baseurl=http://ip/repos
>   gpgcheck=0
>   ```
> - 测试
>
> ```bash
> $ yum list
> ```
>



### CentOS6.6

- 挂载CentOS6.6_Final

  ```
  mount /dev/sr0 /mnt
  ```

- 配置文件

  ```bash
    [DVDISO]
    name=DVD ISO
    baseurl=file:///mnt/   # 大爷的，这里有三个‘/’,踩过坑
    enabled=1
    gpgcheck=0
  ```

