###例子1
```
\#!/bin/bash
 date
```

###例子2
```
vi xx.sh

\#!/bin/bash
echo "文件名:$0"
echo "第一个参数：$1"
echo "第2个参数:$2"
echo "一共有多少个参数$# ,分别的是$*"

chmod +x xx.sh

./xx.sh a b		=>	xx.sh
					文件名:xx.sh
					第一个参数：$1
					第2个参数:$2
					一共有多少个参数3 ,分别的是 a b
```

###例子3
```
\#!/bin/bash
echo "请输入您的名字：" (或者写 read -p "请输入您的名字：" name)
read name					 echo "欢迎$name"
echo "欢迎$name"	
```

###查看当前系统支持那些shell
```
cat /etc/shells

echo $$				=> 	4913
输出当前shell的ID
```

###变量
```
xx = 19		(本地变量，只能影响当前的shell)
定义一个本地变量xx,他的值为19
echo $xx  						=>	19

unset xx
取消变量xx的定义

export yy=10	(环境变量,影响到所有的子shell)
定义一个环境变量 yy,值为10

declare -x cc=10
定义一个环境变量cc，值为10

declare +x cc
把cc改为本地变量

set 
输出所有的本地变量

env 或者直接 export 或者 export -p
输出所有的环境变量

read xx (默认变量为REPLY)
10
给xx赋值，值为10

xx=(aa bb cc dd)
定义一个数组xx，他包含值aa bb cc dd
echo ${xx[0]}
输出aa第一个值   				=> 	aa
echo ${xx[*]} 或者 echo ${xx[@]}
输出数组xx的所有元素 			=> aa bb cc dd
echo ${!xx[*]}
输出所有的下标				=> 0 1 2 3
echo ${#xx[*]}				
输出数组大小					=> 4

declare -r aa
将变量aa设置为只读

readonly aa
将变量aa设置为只读

r=${path#*bo/hh}
定义变量r并把path里面的第一个bo/hh前面的内容都删除

r=${path##*bo/hh}
把最后一个bo/hh前面的所有内容删除，只保留最尾的bo/hh后面的内容

r=${path%*bo/hh}
把第最后一个bo/hh及其后面内容删除

r=${path%%*bo/hh}
把第一个bo/hh及其后面内容都删除

r=${x-"aaaaa"}
判断xx是否存在，如果存在就赋值给r，如果不存在就把aaaaa赋值为r

r=${x:-"aaaaa"}
判断xx是否存在，如果存在且不为空，则赋值给r，如果存在或者为空则把aaaaa赋值给r

r=${x:="aaaaa"}
如果x为空或不存在，则赋值aaaaa给x和r

r=${x="aaaaa"}

r=${x:?"aa"}
如果x不存在或为空，在屏幕打印aa警告

r=${x:+"aa"}

```

###打开子shell
```
bash
打开一个子shell

exit退出当前的shll
```

###限制管理
```
ulimit -a
查看所有的大小限制

ulimit -f 20480
现在创建文件的大小最大为20M
```

###命名命令
```
alias dd="date"
将dd命名为命令date

unalias dd
取消dd的命名
```

###输出命令的先后顺序
```
type -a echo -n
现实echo -n命令里面包含的所有命令
```

###set
```
set -u
开启报错提示

set +u
关闭报错提示

set -x
开启命令跟踪模式(现实当前命令的执行过程)

set +u
关闭命令跟踪模式

```

###命令结果输出到 文件
```
cal > xx
把cal命令的结果输出到xx文件里面，屏幕不显示结果(但会覆盖文件)

cal >> xx
把cal命令的结果输出到xx文件里面，屏幕不显示结果(不会覆盖文件)

cal 2> xx
出错写入（覆盖）

cal 2>> xx
出错写入（追加）

cal 2> hosts 1>&2
正确和错误的都写入（覆盖）

cat > xx < aa
执行写入xx文件的操作 以aa作为写入结束标志
	bbbbb
	cccc
	aaa			=> bbbbb
				   cccc
```

###过滤
```
ifconfig etho | grep 'inet addr'
输出ifconfig的信息，并筛选包含 inet addr的信息
```

###双向重定向
```
ifconfig etho | tee xx | grep 'inet addr'
把ifconfig 信息保存到xx(覆盖) ，并筛选包含inet addr的信息输出

ifconfig etho | tee -a xx | grep 'inet addr'
把ifconfig 信息保存到xx(追加) ，并筛选包含inet addr的信息输出
```

###剪取
```
cut -d: -f1 /etc/passwd
以：作为分割符，获取信息的第一部分
```

###排序
```
cut -d : f3 passwd | sort (这是字符排序)

cur -d : f3 passwd | sort -n (以数字的形式排序)

cur -d : f3 passwd | sort -n -r (从大到小排序)
```

###统计
```
ls -1 / | wc -l 
统计当前目录的文件和文件夹的数量
```

###字符转换
```
tr 'a-z' 'A-Z' < hosts		(这不是正确的命令)
把hosts文件的小写都改为大小输出

tr 'a-z' 'A-Z' < hosts > xxx (标准写法，不会损坏文件)
mv xxx hosts

echo '	a	b' | col -x(或者expand)
把'	a	b'里面的tab都转换为空格输出

```

###结合
```
paste aa bb
把 aa bb文件合并输出（不会修改源文件）
	a11 a22
	b11 b22  			=> a11			a22
						   b11			b22

join aa bb
把 aa bb文件合并输出（不会修改源文件）
	a11 a22
	b11 b22				=> a1122
						   b1122
```

###分割
```
split -b 10k /etc/services xxx
把services分割成M个10K的文件，以xxx作为文件名的开头
		=> xxxaa xxxab xxxac.....

split -l 100 /etc/setvices xxx
把services按每个100行分割

cat xxx* >services 
把所有的分割文件重新组成1个

diff services /etc/services
判断2个文件有什么不同
```

###参数代换
```
find -name 'file*' | xargs ls -l
输出查到的文件的信息
```