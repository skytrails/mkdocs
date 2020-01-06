# linux挂载samba共享

## 命令查看路径

```bash
$ smbclient -L 10.8.8.21 -U public%AM@1974
```



## 挂载

```bash
$ sudo mount //10.8.8.21/Public /mnt -o username="public",password=AM@1974
```



