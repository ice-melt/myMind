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
ls [-l:长列表显示 -a:隐藏文件 -h:所有者] # 列出当前目录下的文件及文件夹列表，
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

### 日期
```bash
date #显示日期
date "+%Y-%m-%d %H:%M:%S" # 按格式输出日期,+不能少
date -s "2019-10-10 10:10:10" # -s 表示设置时间
cal # 以日历方式显示时间,默认显示当前月日历
cal 2019 # 显示2019年日历
```

### 搜索查找类
```bash
find [搜索路径] [选项] 
# -name 文件名 ,按照文件名查找
# -size +20M ,安装文件大小查找,大于+,小于-,等于n
# -user root, 安装文件的拥有着查找 

updatedb # 更新,创建locate文件数据库
locate 文件名 # 快速

grep [-n -i] 文件# 过滤查找,-n显示行号,-i区分大小写
| 		# 管道符号
cat xxx.md |grep keys
```

### 压缩和解压缩
```bash
gzip/gunzip	# 压缩/解压缩,压缩文件成gz文件,解压缩gz文件,不会保留源文件
zip/unzip	# 压缩/解压缩,-r递归压缩/-d制定解压缩目录
# zip -r package.zip /home/
# unzip -d /opt/tmp/ package.zip
tar [选项]		# 压缩成tar.gz
	-A或--catenate：新增文件到以存在的备份文件；
	-B：设置区块大小；
	-c或--create：建立新的备份文件；
	-C <目录>：这个选项用在解压缩，若要在特定目录解压缩，可以使用这个选项。
	-d：记录文件的差别；
	-x或--extract或--get：从备份文件中还原文件；
	-t或--list：列出备份文件的内容；
	-z或--gzip或--ungzip：通过gzip指令处理备份文件；
	-Z或--compress或--uncompress：通过compress指令处理备份文件；
	-f<备份文件>或--file=<备份文件>：指定备份文件；
	-v或--verbose：显示指令执行过程；
	-r：添加文件到已经压缩的文件；
	-u：添加改变了和现有的文件到已经存在的压缩文件；
	-j：支持bzip2解压文件；
	-v：显示操作过程；
	-l：文件系统边界设置；
	-k：保留原有文件不覆盖；
	-m：保留文件不被覆盖；
	-w：确认压缩文件的正确性；
	-p或--same-permissions：用原来的文件权限还原文件；
	-P或--absolute-names：文件名使用绝对名称，不移除文件名称前的“/”号；
	-N <日期格式> 或 --newer=<日期时间>：只将较指定日期更新的文件保存到备份文件里；
	--exclude=<范本样式>：排除符合范本样式的文件。
```
