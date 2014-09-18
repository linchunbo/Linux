###例子1
```
grep 't..' aa --color
在aa文件里面查找包含t..的行
```

###例子2
```
grep 'to\{3,4\}m' aa --color
在aa文件里面查找 t和m之间有 3-4个o的行
```

###例子3
```
ifconfig ech0 | grep 'inet addr' | awk '{print $2}' | awk -F: '{print $2}'
获取ip地址
```

###sed
```
sed '1,2d' aa	(没有改变原文件)
删除aa文件的第一和2行现实修改后的结果显示到屏幕

sed -i '1,2d' aa 	(改变原文件)

sed 's/a/A/g' aa
把aa文件的所有a都替换为A

sed -f yy xx
```

###awk
```
-F：
以：作为分段

默认是空格作为分段

awk -F: '{print NR,$0,NF}' aa
将aa文件每一行以：作为分段，并且显示行号和段数
```