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

###查看命令的默认格式
```
alias rm
查看rm 命令的 完整格式 => rm -i
```

###查看文件名
```
basename path/aa
查看aa的文件名        => aa
```

###查看文件路径
```
dirname path/aa
查看aa的文件路径      => path  
```

###查找命令的路径
```
which passwd
查找passwd命令在哪个路径下 	=> /user/bin/passwd
```

###获取命令结果
```
echo " xx `hostname` xx "
这里重点的是2个反引号		=> xx www.walter.cc xx
```

###查找命令的路径2
```
whereis ls
查找与ls有关的所有路径

whereis -b ls
仅查看命令路径

whereis -m ls
仅查看帮助文档路径
```

###查找命令3
```
locate walter
查找所有与walter有关的路径，不一定用来查找命令
```

###查找文件
```
find 目录 -属性 值 
		属性：	name			文件名
				size			文件大小
				user			所有者
				group			所有组
				uid				用户id
				ctime			创建时间 天
				cmin		   	创建时间	分
				newer			创建时间	新
				perm			文件权限

find / -name walter
从根目录开始查找文件名为walter的所有文件

find / -user walter -group walter
从根目录开始查找 所有者和所有族都为walter的文件 

find / -name walter or -group walter
从根目录开始查找 所有者为walter 或者 所有族为walter的文件

find -size 4M
当前路径下查找 大小为4M的文件

find -size +2M -size -5M
当前路径下查找 大小大于2M 小于5M的文件

find -ctime +1
在当前路径下查找 创建日期大于1天的文件

find -newer file1
在当前路径下查找 比file1要新的文件

find -perm 222
在当前的路径下查找 权限为222的文件
```

###查看磁盘信息
```
dumpe2fs /dev/sda3
查看磁盘sda3分区的信息
```

###查看系统支持那些编码
```
locale -a
```