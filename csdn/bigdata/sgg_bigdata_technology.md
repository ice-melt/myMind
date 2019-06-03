# csdn上的《大数据技术》课程笔记(尚硅谷)

## 学习进度
-[ ] 进度10/53

## 大数据技术之linux 

### 常用的ssh，ftp工具：  
XSheel5,XFTP，SecureCRT

### vm 网络与母机连接的三种方式：  
桥接（bridge）：与主机在同一网段  
NAT（network address transfer）：与主机不在同一网段，可以访问主机网段其他ip  
仅主机模式（Host-Only）：只能与主机连接  

### 常用的linux命令:

#### 1.	 vi 和 vim 快捷键
1. `yy`复制当前行，`5yy`复制当前行及后面4行，`p`表示黏贴
2. `dd`删除当前行，`5dd`删除当前行及后面4行
3. 输入`/`+`关键字`，<kbd>Enter</kbd>查找，`n`查找下一个
4. 设置和取消行号 `:set nu` 和 `:set nonu`
5. 正常模式下快速到首行`gg`，快速到尾行`G`
5. 取消动作，回到正常模式输入`u`
5. 移动光标到制定行，显示行号输入想到达的行，<kbd>Shift</kbd>+<kbd>g</kbd>
#### 2. 关机，重启	
```bash
#立即关机
shutdown -h now
#1min之后关机
shutdown -h 1
#立即重启
shutdown -r now
# 关机
halt
# 重启系统
reboot
# 把内存的东西同步存到磁盘
sync
```

#### 3. 用户的登录和注销
```bash
#注销用户
logout
#指定运行级别
init [x]  # x \in {0-6}
#查看运行级别
runlevel
#忘记密码，
#开机引导时输入回车>e>编辑内核，最后增加1 进入单用户模式
#此时无需密码，
#用passwd给root用户重新设置密码
```

### linux用户管理
```bash
# 添加用户
useradd [选项] 用户名

-d 指定用户目录（不指定目录会自动创建与用户同名的目录）
-g 指定用户组 （不指定会自动创建与用户同名的组）
# 给用户设置密码（新增或修改）
passwd 用户名

# 删除用户
userdel [选项] 用户名

-r 删除用户家目录（不指定会保留家目录）

# 查询用户信息
id 用户名
whoami # 当前用户

# 创建组
groupadd 组名
# 删除组
groupdel 组名
# 修改用户组
usermod -g 组名 用户名

#用户配置	/etc/passwd
#组配置	/etc/group
#密码		/etc/shadow
```

### 帮助指令，文件目录类指令
```bash
man 命令或配置文件
help 命令

pwd #显示当前目录路径
ls [-l -a] #列出当前目录下的文件及文件夹列表，
cd ~ #回到用户目录
cd .. #返回到上一层目录
mkdir [-p] 目录路径 # 创建目录，-p可以一次创建多级目录
rmdir 目录 #只能删除空目录
rm -rf 目录 #递归删除整个目录，-r递归，-f强制

touch 文件名 [文件名2 文件名3 ...] # 创建一个空文件
cp [-r] source dest # 复制文件从 source 到 dest
					# -r 递归复制整个文件夹
mv oldfilename newfilename # 重命名
mv filepath newfilepath # 移动

cat [-n] 文件名 [| more] #以只读方式查看文件,-n 显示行号
				# | 管道符，more以全屏方式分页显示，有一些快捷键，
				# enter，空格，ctrl+f，ctrl+b，q，=,:f

less 文件名 # 分屏查看文件内容，根据需要加载文件

ls -l > xx.txt		# 输出重定向,覆盖写入
ls -la >> xx.txt	# 追加	

echo $PATH
head [-n 5] 文件名 	# 显示文件开头，-n 5显示文件前5行，默认显示10行
tail [-n 5 -f] 文件名 	# 显示文件后面内容，-n 5 显示后5行，-f实时查看其他人写入文件内容

ln -s /root /linkToRoot # 软连接（符号链接），类似快捷方式
history [x] # 历史使用的命令,可以指定显示条数
!x # 执行指定历史行号的命令
```

