# 好芝生物PCR仪安装部署说明书

## 系统部署

- 安装Ubuntu LTS16.04操作系统（参考Ubuntu系统安装，语言选择中文）

- 扫码功能配置

  - NLS-FR40xx-3x用户手册32页

  - 依次扫码【开启设置码】【设置为usb虚拟串口】【关闭设置码】

  - 检查是否存在/dev/ttyACM0文件，存在则说明成功。

  - 检查ttyACM0文件权限（要支持hg用户读权限)  / 或者直接设置为: 

    ```bash
    sudo chmod 777 /dev/ttyACM0
    ```

  - 扫码成功后重启系统

  - 设置完成

- 安装png图片转换工具

  ```bash
  $ sudo apt-get install unoconv
  ```

- 安装中文输入法

  - ```bash
    $ sudo apt-get install ibus-pinyin
    ```


- 执行安装脚本

  ```bash
  $ sudo ./install.sh
  ```

  