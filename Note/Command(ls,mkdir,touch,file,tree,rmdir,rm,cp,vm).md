###显示当前所在的目录
```
pwd
```

###目录
```
ls [/目录]
不写目录，默认为当前目录
例如显示 home下面有什么文件：ls /home

ls -l [/目录]
详细查询目录

ls -1 [/目录]
将文件一行一个的列举出来

ls -a [/目录]
显示所有的文件，包括隐藏的

ls -s [/目录]
显示文件，以及其大小

ls -h [/目录]
显示文件的大小的单位

ls -ld
查看当前目录的属性

ls -i xx
查看xx文件的存储信息（inode）

ls -v xx
查看xx文件的存储信息(block)

```

###创建文件夹
```
mkdir aa
在当前的目录下创建 名为aa的文件夹

mkdir -p aa/bb
在aa目录下创建 bb 文件夹，aa不存在，会先创建aa

mkdir -p aa/{xx,zz,cc}
在aa目录下创建 xx zz cc 3个文件夹
```

###创建文件
```
touch bb
在当前的目录下创建 名为bb的文件
```

###查看类型信息
```
file xxx
查看xxx的类型信息
```

###树型结构显示文件目录
```
tree [目录]
以树型的方式显示目录结构，不写目录的时候，默认是当前目录
```

###目录跳转
```
cd = cd ~
跳转到当前用户的家目录

cd ..
跳转到上一级

cd [目录]
跳转到指定的目录

cd -
退回到上一次打开的目录，不是上一级
```

###目录删除
```
rmdir aa
删除 aa 文件夹

rmdir -p aa/cc
删除 cc 文件夹，如果删除之后aa文件夹为空，那么会把 aa 也删除
```

###删除
```
rm -rf aa
强制删除 aa，如果aa是文件夹，则会递归删除aa下面的所有文件，即删除aa所有
```

###复制
```
cp [选项] ../path1/xx /path2/yy
如果yy为文件夹，则拷贝 path1下面的xx到 yy里面
如果yy不是文件夹，则拷贝 xx 到 path2下面，并且命名为yy

cp -rf path1 path2
将 path1内容 完全复制到 path2里面

cp -rfp path1 paht2
将 path1内容和属性信息都 完全的复制到 path2里面

cp -u path1/aa path2/aa
如果 path1/aa 比 path2/aa新，则复制覆盖，否则不执行

cp aa bb
无论aa是不是快捷方式，拷贝的bb也不是快捷方式

cp -b aa bb
如果aa为快捷方式，拷贝的bb也是快捷方式
```

###剪切(跟cp一样)
```
mv [选项] path1/aa path2/bb
如果 bb为文件夹，剪切过去， 如果bb不是文件夹，则剪切过来，重命名为bb
```
