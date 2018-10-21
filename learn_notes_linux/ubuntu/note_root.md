## Ubuntu18.04 下修改 root密码

```Bash
	ice-melt@Y430P:~$ sudo passwd root
	[sudo] password for ice-melt: 
	Enter new UNIX password: 
	Retype new UNIX password: 
	passwd: password updated successfully
	ice-melt@Y430P:~$ su root
	Password: 
	root@Y430P:/home/ice-melt# 
```

备注：

	#符号 是系统用户 root
	$符号 是你创建的用户 没指定权限！ 