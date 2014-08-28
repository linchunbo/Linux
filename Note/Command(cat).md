###查看文件内容1(适合小文件)
```
cat xxx
查看 xxx文件的所有内容（从第一行到最后一行）

cat xxx -n
查看文件内容时 在前面加上行号
```

###查看文件内容2
```
tac xxx
查看 xxx文件的所有内容（从最后一行到第一行）

```

###查看文件内容3
```
nl xxx
查看 xxx文件内容 无视空行

nl -b a xxx
查看 xxx文件内容 不无视空行（等同于 cat xxx -n）
```

###查看文件内容4（可以用来看大文件,不能往前翻）
```
more  xxx
分屏查看 xxx文件

按回车 一行一行往后显示
按空格 一页一页往后显示
/字符串 = 高亮要查询的字符串
```

###查看文件内容5
```
less xxx
分屏查看xxx

按回车 一行一行往后显示
按空格 一页一页往后显示
按pguP 往前一页一页看
按pgdn 往后一页一页看
按home 跳转到文章最开头
按end 跳转到文章的末尾

/字符串 = 高亮要查询的字符串
```

###查看文件内容6
```
head -5 xxx
查看xxx文件的前5行
```

###查看文件内容7
```
tail -3 xxx
查看晚间的尾3行

tail -f xxx
实时查看文件的尾10行
```

###查看文件内容8
```
tailf xxx
实时查看文件的尾10行（同 tail -f xxx）
```

###查看文件内容9
```
od -t c xxx

```

###查看文件内容10
```
strings xxx
以字符串形式查看文件（可以用来看2进制文件,非文本文件）
```