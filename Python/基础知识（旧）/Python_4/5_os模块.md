# OS模块

## 文件操作

| 名称| 说明| 示例|
|---|---|---|
rename|重命名文件|`os.rename(原文件，新文件名)`
remove|删除文件|`os.remove(文件名)`

## 目录管理

| 名称| 说明| 示例|
|---|---|---|
listdir|目录列表|os.listdir(目录名)
mkdir|创建目录|os.mkdir(目录名)
rmdir|删除目录|os.rmdir(目录名)
getpwd|获取当前目录|os.getpwd()
chdir|修改工作目录|os.chdir
|path.dir|判断是否是文件|os.path.isdir(目录路径)