###压缩1(很少用)
```
Compress -v xx
压缩xx文件，并删除源文件

Compress -c -v xx > xx.Z
压缩xx文件，但不删除源文件
```

###压缩与解压1
```
gzip xx
压缩xx为xx.gz，并且删除源文件

gzip -d xx.gz
解压xx.gz

gzip -c xx > xx.gz
压缩xx为xx.gz但不删除源文件
```

###压缩与解压2
```
bzip2 xx
压缩xx文件为xx.bz2

bzip2 -d xx.bz2
解压xx.bz2

bzip2 -c xx > xx.bz2
压缩xx为xx.bz2且不删除源文件

```

###解压1
```
uncompress xx.Z
解压xx.Z文件
```

###查看 gz压缩文件内容
```
zcat xx.gz
查看xx.gz压缩文件的内容

```

###查看 bz2压缩文件内容
```
bzcat xx.bz2
查看xx.bz2压缩文件的内容
```

###压缩2
```
zip xx.zip xx
压缩xx为xx.zip
```

###解压2
```
unzip xx.zip
解压xx.zip
```

###打包，归档(没有压缩功能，文件不会缩小)
```
tar cvf xx.tar xx
将xx文件打包为xx.tar

tar cvf xx.tar xx --remove-files
将xx文件打包为xx.tar并删除源文件

tar tvf xx.tar
查看xx.tar里面打包了什么文件

tar xvf xx.tar
解档xx.tar文件

tar xvf xx.tar -C aa/
解档xx.tar到aa文件夹里面

tar cvf xx.tar *
将当前目录所有文件打包

tar xvf xx.tar aa
只把aa文件从xx.tar 里面解档出来

tar zcvf xx.tar.gz *
打包并进行gzip压缩

tar zxvf xx.tar.gz
解压并解档xx.tar.gz

tar jcvf xx.tar.bz2 *
打包并进行bizp2压缩

tar jxvf xx.tar.bz2
解压并解档xx.tar.bz2
```

###备份
###增量备份(在原先的基础上备份增加的东西)
###差异备份(每一次都将与全备份差异的部分备份)
```
dump -数字
	  0				全备份
	  1...
      0,0,0,..		全备份
	  0,1,2,3..		增量备份
	  0,...3,2.1	差异备份

dump -0u -f xx/1.dump /dev/sda3
完全备份sda3的数据，并把相关信息写入到1.dump

dump -1u -f xx/2.dump /dev/sda3
增量备份sda3的数据，并把相关信息写入到2.dump

```

###回复备份
```
restore -t -f xx/1.dump
不回复备份，但查看备份1.dump的内容

restore -r -f xx/1.dump
回复1.dump的备份	

restore -i -f xx/1.dump
进入1.dump备份文件
	add aa bb
	只回复aa bb文件
```

###光盘写入
```
mkisofs -o xx.iso file1 file2 file3
创建xx.iso文件并把file1 2 3写入到xx.iso文件
```

###光盘刻录
```
Cdrecord
```

###
```
dd if=/dev/zero of=file4 bs=1M count=1

dd if=/dev/sda3 of=test
把sda3的数据，所有数据，一点一点拿出来，组成test文件

dd if=test of=/dev/sda3
把test的东西拷到sda3
```

###打包解包
```
find -name 'file*' | cpio -o(打包) > xx.cpio
将当前查到的文件，传给cpio ，打包成xx.cpio

cpio -iu < xx.cpio
将xx.cpio解档出来
```

