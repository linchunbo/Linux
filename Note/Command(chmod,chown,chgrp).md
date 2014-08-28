###文件权限
```
chmod 参数 文件名

chmod u=rwx,g+w,o-r xxyy
对于xxyy文件,用户的权限为rwx,组增加W权限，组以外的人减去阅读的权限

chmod a=r xxyy
对于xxyy，所有人的权限都是r

chmod +r xxyy
对于xxyy，所有人的权限都加r

chmod 755 xxyy
文件xxyy对应 用户权限为rwx,组为rx,其他人为rx

chmod -R 755 rece
将文件夹 rece以及该文件夹里面所有的子文件的权限都设置为755(-R 表示递归)

```

###文件所有者
```
chown [-R] bo xxyy
将xxyy的所有者改为bo

chown [-R] bo:bo xxyy
将xxyy的所有者改为bo,所有族改为bo
```

###文件所有族
```
chgrp [-R] walter xxyy
将xxyy的所有族改为walter
```

###权限过滤
```
umask
查看系统的过滤权限    		=> 0	0	2	2
								u 	g	o
umask 333
改变系统的过滤权限为 0333

umask -S
显示过滤完后的默认权限
```

###查看文件的操作权限
```
lsattr aa
查看 aa 文件的操作权限		=>
```

###改变文件的操作权限
```
chattr +a aa

a    	只能添加，不能删除
i		不能添加，也不能删除，就是不能修改

```

###文件的特殊权限
```
```