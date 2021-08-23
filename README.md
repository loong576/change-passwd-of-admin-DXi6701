## 一、背景

昆腾的虚拟带库web管理界面Administrator用户密码遗失，现需要修改。

## 二、登陆管理页面

http://172.16.xx.xx，172.16.xx.xx为虚拟带库地址

![image-20210811171307959](https://i.loli.net/2021/08/11/Ig2tsxvfTiR5jVy.png)

## 三、登陆系统

使用crt远程登陆虚拟带库

虚拟带库root用户的默认密码为Qa@SmX7!

## 四、密码修改

密码修改有两种方式

### 1.密码修改方式一

```bash
[root@VTL ~]# cd /opt/DXi/
[root@VTL DXi]# ./syscli --change password --name admin
Enter old password: 
Enter new password: 
Enter new password again: 

Command completed successfully.
```

使用syscli命令修改，这种方式有个坑爹的地方是必须知道之前的密码，不然修改不成功。由于之前的密码遗失，本文使用第二种方式重置密码。

### 2.密码修改方式二

```bash
[root@VTL DXi]# passwd admin
Changing password for user admin.
New UNIX password: 
BAD PASSWORD: it is too short
Retype new UNIX password: 
passwd: all authentication tokens updated successfully.
```

直接使用passwd命令修改用户admin密码，当再次登录web时，Administrator密码即为刚刚修改的admin密码。

## 五、登录系统

![image-20210811172257156](https://i.loli.net/2021/08/11/Q1sB4kXZbWxTRSP.png)

系统登录成功
