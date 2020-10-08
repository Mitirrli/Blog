---
title: "Php Command Script"
date: 2020-10-08T10:20:58+08:00
draft: true
---

# 有用的php命令行命令

###### 1. 查看当前已安装的扩展
```shell script
$ php -m 
```

###### 2. 查看当前php版本
```shell script
$ php -v
```

###### 3. 查看扩展版本
```shell script
$ php --ri 扩展名
```

###### 4. 快速查看扩展版本
  
```shell script
$ php -i | less
```

###### 5. 查看php配置文件路径

```shell script
$ php -i | grep php.ini
```

###### 6. 执行文件(检查代码语法是否正确)
```shell script
$ php -f 文件名
```

###### 7. 直接执行代码
```shell script
$ php -r 'echo 1;'
```

###### 8. 检查代码语法
```shell script
$ php -l 文件名
```

###### 9. 查看帮助
```shell script
$ php -h
```

###### 10. 查看当前php可执行文件位置
```shell script
$ which php
```

###### 11. 开启服务 

```shell script
$ php -S 0.0.0.0:1234
```

###### 12. 读取特定的ini文件

```shell script
$ php -c /usr/local/etc/php/php.ini
```




