# csdn上的《大数据技术》课程笔记(尚硅谷)

## 学习进度
-[ ] 进度10/53

## 大数据技术之Shell

### Shell 解析器
```bash
/bin/sh
/bin/bash
/sbin/nologin
/bin/dash
/bin/tcsh
/bin/csh
```
### Shell 格式
```bash
#!/bin/bash
```
### 变量
```bash
# 系统变量
$SHELL $PWD $HOME $USER 

# 自定义变量
变量=值		# 等号两侧不能有空格
unset 变量	# 撤销变量
readonly 变量	# 只读变量,不能被unset
# 字母数字下划线组成,不能以数字开头
# 变量默认类型是字符串,不能进行数值运算
# 变量值有空格,需要使用引号括起来(单双均可)

export 变量	# 提升变量到全局可用

# $n
$0	# 脚本本身
$1-${x} # 代表第1-x个参数,10以上的参数需要用大括号包含

$#	# 获取所有输入参数个数,常用于循环
$*	# 代表命令行的所有参数,所有参数当成一个参数 "$*"
$@	# 代表命令行的所有参数,所有参数会分别处理 "$@"
$?	# 上一条语句是否正确执行,返回0代表正确执行,其他代表脚本错误	
```

### 运算符
```bash
# 基本语法
$((运算式))
$[运算式]
expr +,-,\*,/,% 	# 加减乘除取余,expr运算符间有空格

# expr 3 + 2 

```
### 条件判断
```bash
[ condition ] 	# condition前后有空格
# 注意,条件非空即为true,[] 返回false

# 常用判断条件
=	# 字符串比较

-lt	# 小于
-le	# 小于等于
-eq	# 等于
-gt	# 大于
-ge	# 大于等于
-ne	# 不等于

-r	# 有读的权限
-w	# 有写的权限
-x	# 有执行的权限

-f	# 文件存在并且是一个常规的文件
-d	# 文件存在并且是一个目录
-e	# 文件存在

# [ 23 -ge 22 ]
# [ -w helloworld.sh ]
# echo $? 	# 返回0

# 多条件判断
&&	# 前一条命令执行成功,才执行后一条命令
||	# 上一条命令执行失败后,才执行下一条命令
```

### 流程控制

```bash
# if判断,if后要有空格,条件判断式前后要有空格

if [ 条件判断式 ];then
	程序
fi

if [ 条件判断式 ]
then
	程序
fi

# case语句

case $变量名 in
	"值1")
		程序1
	;;
	"值2")
		程序2
	;;
	*)
		程序默认
	;;
esac

# for 循环 type1
for(( 初始值;循环控制条件;变量变化 ))
	do
		程序
	done
s=0

# for 循环 type2
for 变量 in 值1 值2 值3
do
	程序
done

# while 循环
while [ 条件判断式 ]
do
	程序
done
```

一些bash脚本demo

```bash
for((i=1;i<=100;i++))
do
        s=$[$s+$i]
done
```

```bash
for i in $*
do 
        echo "输入 $i"
done
```

```bash
#!/bin/bash
s=0
i=1
while [ $i -le 100 ]
do
	s=$[$s + $i]
	i=$[$i + 1]
done
echo $s
```
### read 读取控制台的输入

```bash
#!/bin/bash
read -t 7 -p "input your name" NAME
echo $NAME
```

```bash
read(选项)(参数)
选项:
-t 指定读取值时等待的时间(秒)
-p 指定读取值时的提示符
参数:
变量:指定读取值的变量名
```
### 函数
```bash
basename /home/$USER/test.txt
> test.txt

dirname /home/$USER/text.txt
> /home/$USER

# 自定义函数
[ function ] funname[()]
{
	Action;
	[return int;]
}

funname

# 注意:	1.调用函数前先声明函数
#		2.返回值只能通过$?系统变量获得
#		3.加return返回,否则返回最后一条命令的运行结果
# 		4.return 后跟数值n(0-255)	
```

```bash
#!/bin/bash

function sum()
{
	s=0;
	s=$[$1+$2]
	echo $s
}

read -p "input your param1:" P1
read -p "input your param2:" P2

sum $P1 $P2
```
### Shell工具
#### cut
```bash
cut [选项] filename # 从文件中剪切数据
# 选项参数
-f 列号,提取第几列
-d 分隔符,默认\t

# eg: 	
#	cut -d " " -f 2,3 cut.txt
#	cat cut.txt | gerp guan |cut -d " " -f 1
# 	echo $PATH|cut -d : -f 3-
#	ifconfig eth0
```
#### sed
流编辑器,将处理行存入"模式空间"(缓冲区),
sed处理后将缓冲区内容送往屏幕,继续处理下一行
 
```bash
sed [选项参数] 'command' filename

# 选项参数
-e:	直接在指令列模式上进行sed的动作编辑
# 命令功能
a 	新增,后面可接字符串
d 	删除
s 	查找并替换

# 示例
sed "2a mei nv" sed.txt
sed "/wo/d" sed.txt 	#删除wo
sed "s/wo/ni/g" sed.txt # 全局替换,wo->ni
sed -e "2d" -e "s/wo/ni/g" sed.txt #删除第二行,wo->ni
```

#### awk
文件逐行读入,默认以空格将每行切片,切开的部分再进行分析处理

```bash
awk [选项参数] 'pattern1 {action1} pattern2 {action2} ...' filename

# 选项参数说明
-F 指定输入文件分隔符
-v 赋值一个用户定义变量

# 示例
awk -F : '/^root/{print $1}' passwd
awk -F : '/^root/{print $1","$7}' passwd
awk -F : 'BEGIN{print "user,shell"} /^root/{print $1","$7} END{print "ice-melt,bin/"}' passwd
awk -F : -v i=1 '{print $3+i}' passwd

# 内置变量
FILENAME 文件名
NP 一度的记录数
NF 浏览记录的域的个数(切割后,列的个数)

awk -F : '{print FILENAME","NR","NF}' passwd
ifconfig wlx488ad25287ba|grep "inet"|awk -F " " '{print $2}'
awk '/^$/{print NR}' passwd
```
#### sort
将文件进行排序,并将排序结果标准输出
```bash
sort(选项)(参数)
# 选项
-n 依照参数的大小排序
-r 以相反的顺序排序
-t 设置排序时所用的分隔字符
-k 指定需要排序的列
# 参数:指定待排序的文件列表

sort -t : -nrk 3 sort.sh
```
