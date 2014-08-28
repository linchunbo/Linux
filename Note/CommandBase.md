###命令语法
```
命令 -修饰（可以多个） 参数
命令 -修饰1 -修饰2 ... 参数 == 命令 -修饰1修饰2... 参数
例如：ls -a -l -1 -s /home = ls -al1s /home

命令 --修饰（该修饰是一个整体，即一个单词）
例如查看命令的帮助: ls --help
```

###查看命令的做用
```
whatis ls
查看ls命令 有什么做用
```

###查看命令的详细用法
```
ls --help
查看ls命令 详细使用方法
```

###查看命令的帮助手册
```
man [章数] passwd 
查看passwd命令第一章的手册(章数不写，默认是1)

在手册里面打 /root
高亮 root 单词

在手册里面打/^DESC
高亮DESC开头的单词

按q退出

man -k clock
查看所有的包括 clock 字串的命令

man 文件名
查看指定文件的用法
```

###查看命令帮助2
```
info passwd
查看passwd命令的用法，跟map差不多
```

###用户切换
```
su - [用户名]
不写用户名，默认为root
例如将当前用户切换为walter：su - walter
```

###查看当前的允许级别
```
runlevel
```

###切换允许级别
```
init 级别[0-6]
```

###查看命令历史
```
history
显示本次命令编辑输入过的所有命令
```

###调用历史命令
```
!22
执行历史记录里面第22次输入的命令
```

###退出功能命令
```
quit
```

###清空命令编辑器
```
clear  = 快捷键 Ctrl + l
```

###退出当前终端
```
exit = 快捷键 Ctrl + d
```

###gedit文本编辑器
```
gedit
使用gedit打开一个新的文本

gedit xxyy
使用gedit打开xxyy文本
```

###nano文本编辑器
```
nano
使用nano打开一个新的文本

nano xxyy
使用nano打开xxyy文本
```

###系统查看
```
uname
查看系统的名字

uname -i
系统版本

uname -r 
内核版本

uname -a
所有的信息
```

###查看系统信息2
```
lsb_release -a
查看系统的信息
```

###输出
```
echo $PATH
输出当前默认的命令执行的绝对路径
```

###增加默认的命令执行路径
```
PATH= 复制PATH然后后面添加 "：/home/walter"
将/home/walter 这个路径加入到命令执行的默认路径 = 之后不用打./来执行当前的命令
```