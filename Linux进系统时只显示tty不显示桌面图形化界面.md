tty之间的切换：Ctrl + Alt + F1/F2/F3...

更新的时候出错，下次开机就会进不了桌面图形化界面

解决办法就是：删除更新的东西

```
1. sudo rm /var/lib/dpkg/updates/*
2. sudo apt-get update
3. sudo apt-get upgrade
```

详细学习可以参考链接：http://ubuntuforums.org/archive/index.php/t-941125.html
