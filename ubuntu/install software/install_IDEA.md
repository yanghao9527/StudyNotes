# 安装IDEA

## 官网下载IDEA安装包

[官网](https://www.jetbrains.com/idea/download/#section=linux)

## 解压到指定目录

运行以下命令
```shell
sudo tar -zxvf xxxxx.tar.gz -C /usr/local/bin/
```

## 给权限

```
#切换到所在目录
cd /usr/local/bin
ls
#给idea目录赋权限
sudo chmod 755 xxxxxx
```

## 执行安装脚本
```
sh xxxxxx/bin/idea.sh
```
## 手动创建图标

```
打开系统软件图标文件
cd /usr/share/applications

创建图标文件
sudo vim Pycharm.desktop
输入内容
[Desktop Entry]
Name=IDEA
Comment=IDEA
Exec=/usr/local/bin/idea-IU-211.7142.45/bin/idea.sh
Icon=/usr/local/bin/idea-IU-211.7142.45/bin/idea.png
Terminal=false
Type=Application
Categories=Utility;Application
```

yanghao_tut_mail@stud.tjut.edu.cn

