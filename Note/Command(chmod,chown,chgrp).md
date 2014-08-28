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
