# TeamViewer安装方法

##依赖包安装

```bash
sudo apt-get install libqt5x11extras5
sudo apt-get install qml-module-qtquick-controls
sudo apt-get install qml-module-qtquick-dialogs
```

## 安装packets

~~~bash
sudo dpkg -i tv.deb		
~~~



## 注意事项

- 若执行dpkg -i tv.deb命令后，出现安装不了其他依赖的情况则执行以下命令：

~~~bash
sudo apt-get remove teamviewer
~~~

