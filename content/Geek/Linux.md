---
title: Linux
---


添加新用户：
```
# useradd newusername -d /home/newusername # newusername 为新用户的名字
```

设置密码：
```
# passwd newusername # newusername 为新用户的名字
```

```
$ apt list --upgradable # 查询可更新的软件
$ apt-cahe search packageName # 搜索文件名含packageName字段的包
```

```
$ fc-list :lang=zh-cn # 查询系统中的中文字体
```

```
$ rsync -au --delete --progress folderSrc  folderDest # 文件同步，folderSrc源，folderDest 目标
```

curl 下载文件
```
curl -o output.txt http://aaaa/output.txt
```


