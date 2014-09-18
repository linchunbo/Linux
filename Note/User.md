###group
```
group walter
查看walter的组
```

###groups
```

```

###gpasswd
```
gpasswd -a tom walter
把tom 加进walter的组

gpasswd -A tom bo
把tom设置为bo组的管理员

gpasswd -d tom bo
把tom从bo组里面删除
```

###newgrp
```
newgrp walter
把主组设置为walter
```

###useradd
```
useradd bo
添加用户bo

useradd -c "im bo" -s /sbin/nolongin -d /bo -g bo -G walter -u 1000
添加用户bo 名称 imbo shell目录/sbin/nolongin 家目录/bo  bo是主组，walter是附主组 uid 1000
```

###usermod
```
usermod -s /bin/bash bo
更改用户bo的shell目录

usermod -c "xxxx" bo
更改bo的名字

usermod -L bo
锁住用户bo

usermod -U bo
解锁用户bo
```

###passwd
```
passwd bo
修改bo的密码

passwd -d bo
清空bo的密码

passwd -S bo
查看bo密码的状态

echo aa | passwd --stdin bo
标准输入密码

passwd -l bo
锁住bo的密码

passwd -u bo
解锁bo的密码

passwd -20 bo
bo用户只有20天使用

```

###userdel
```
userdel -r bo
删除用户bo
```

###chage
```
chage -d 2009-09-18 bo
修改bo密码信息的 最后一次修改密码的时间

chage -E 2012-12-21 bo
修改bo用户在2012-12-21过期

chage -m 10 -M 20 -W 7 bo
bo用户最小的修改密码时间为10天，密码最晚修改时间为20天，提前7天警告修改密码

chage -I 4 bo
超过时间不修改密码，则有4天强制修改时间，如果在不修改，则锁住账号

chage -l bo
列出bo的账户信息
```

###finger
```
finger tom
查看tom的账户属性信息
```

###chfn
```
chfn tom
改变tom的账户属性信息
```

###chsh 
```
chsh -l
查到当前用户支持那些shell路径

chsh -s /sbin/nologin bo
修改bo的shell目录为/sbin/nologin
```

###id
```
id bo
查看bo的uiid等信息

id -nG bo
查看bo的组
```

###groupadd
```
groupadd bo
添加bo这个组
```

###groupdel
```
groupdel bo
删除bo这个组
```

###getfacl
```
getfacl xx
获取xx文件的访问控制列表
```

###setfacl
```
setfacl -m u:tom:rw- xx
对xx设置访问控制列表 给予tom用户tw权限

setfacl -x u:tom xx
取消tom用户对于xx文件的特殊权限

setfacl -m g:tom:rw- xx
设置tom组对于xx文件的特殊权限

setfacl -m d:u:bo:rwx xx/
对于xx文件夹里面的任何文件对于bo都有默认权限rwx
```

###sudo
```
sudo -k
清空缓存

sudo mount /dev/cdrom /mnt
以非root用户执行mount命令
```

###visudo
```
visudo (等于 vim /etc/sudoers)
tom www.bo.com=NOPASSWD:(root)/bin/mount
给予tom用户以root的身份使用mount的权限
```