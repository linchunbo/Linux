###磁盘管理
```
boot sector
super block			记录各个block group的信息（从哪开始到哪结束）
inode				记录文件的属性信息(记录一个文件消耗128字节)
block				存储文件的块，块越大，查询就会快，但浪费，块越小，查询慢，浪费少

```