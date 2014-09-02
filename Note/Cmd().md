###查看磁盘信息
```
df
显示已挂载的文件系统的信息

df -h

df -ht

```

###查看文件夹
```
du /etc
查看etc文件夹，及其里面的东西的大小

du -s /etc
只查看etc文件夹的大小，不显示里面的东西
```

###创建软连接（快捷方式）
```
ln -s aa aa1
创建aa 文件的 快捷方式 aa1
```

###创建硬连接(与复制的区别是，硬连接存储的block和原文的是同一个)
```
ln aa aa2
给aa文件创建一个 硬连接文件 aa2
```

###显示系统的所有硬盘和对应的分区
```
fdisk -l
显示系统的所有硬盘和对应的分区

fdisk -l /dev/sda
显示sda硬盘和它对应的分区

fdisk /dev/sda
给sda硬盘创建分区
```

###更新硬盘分区表
```
partprobe /dev/sda
更新sad硬盘的分区
```

###格式化
```
mkfs -t ext3 /dev/sda5
将sda5分区格式化 ext3格式

mkfs -t ext3 -b 4096 /dev/sda5
将sda5 格式化成4M的空间的ext3格式

mkfs.
```

###挂载
```
mount /dev/sda5 /mnt
把sda5挂载到mnt文件夹

mount -o remount,ro /mnt
以只读的形式重新挂载mnt

mount -o remount,rw /mnt
以可读可写的形式重新挂载mnt

mount -o remount,noexec /mnt
以没有可执行权限的形式重新挂载mnt

mount -o remount,exec /mnt
以可执行权限的形式重新挂载mnt 

mount -o loop xx.iso /mnt
挂载镜像文件
```

###取消挂载
```
umount /dev/sda5
取消挂载sad5分区

```

###整个分区检查
```
fsck -f /dev/sda5
强制检查sda5分区

fsck -f -c /dev/sda5
检查sda5并显示进度
```

###检查硬盘坏道
```
badblocks /dev/sda5
检查并显示sad5分区的坏道

badblocks -sv /dev/sda5
显示检查的进度和结果
```

###查看分区的使用进程
```
fuser -mv /mnt
查看那些进程使用了mnt
```

###开机自动执行挂载
```
打开/etc/fstab
根据格式输入 /dev/sda5			/mnt	ext3	defaults	0(是否每天不备份) 0（是否每天都检查）
```

###查看磁盘参数
```
tune2fs -l /dev/sda5
查看sad5分区的信息

tun2fs -L xx /dev/sda5
将sad5的卷标改为XX

tun2fs -h
查看tun2f2命令的参数
```

###格式化交换分区
```
mkswap /dev/sda6
将sda6格式化成交换分区
```

###激活交换分区
```
swapon /dev/sda6
激活交换分区sda6
```

###取消交换分区
```
swapoff /dev/sda6
取消交换分区sda6
```

###给分区起别名
```
e2label /dev/sda5 xx
将sda5的别名改为xx

e2label /dev/sda5
查看sda5的别名
```