# 美化 Ubuntu 20.04

## 安装后续需要用到的软件

```shell
$ sudo apt install gnome-tweak-tool gnome-shell-extensions chrome-gnome-shell
$ sudo apt install gtk2-engines-murrine gtk2-engines-pixbuf 
$ sudo apt install sassc optipng inkscape libcanberra-gtk-module libglib2.0-dev libxml2-utils
```



https://www.gnome-look.org/p/1403328/

https://zhuanlan.zhihu.com/p/176977192

https://www.cnblogs.com/feipeng8848/p/8970556.html



## 安装 Tweaks 

```shell
sudo apt install gnome-tweak-tool
```

## 手动安装 Dash To Dock

下载文件

解压

重命名

移动到文件夹 /home/.local/share/gnome-shell/extensions


Alt+F2 再输入 r 重启桌面

终端输入 gnome-tweaks 打开 Tweaks


## 下载主题和图标

下载文件

移动文件夹

```shell
sudo mv xxxxx /usr/share/themes

sudo mv  xxxx /usr/share/icons
```

## 设置 Tweaks

更改按键位置

更改 Dock 位置，大小，自动隐藏

重启