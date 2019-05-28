# Ubuntu 18.04 常用软件安装

## 前言

又一次重新安装Ubuntu，想把装机过程的过程记录下来方便后续学习印证


## 安装搜狗输入法

#### fcitx框架

搜狗拼音需要fcitx框架,18.04可以直接在软件中心搜索下载

下载完成后打开`语言支持`将`键盘输入法系统`修改为`fcitx`,并`应用到整个系统`

#### 安装

`sudo dpkg -i sogoupinyin_*.deb`

安装搜狗输入法有可能遇到的问题:

1. 不管什么问题,正常安装后可先尝试重启系统后查看问题是否解决

2. Ubuntu18.04搜狗拼音输入法候选栏无法显示中文（英文乱码）

```bash
cd ~/.config
rm -rf SogouPY* sogou*
```	
## 安装sublime-text3

#### 安装

`sudo dpkg -i sublime-text_bulid-3208_amd64.deb`

#### 破解
适用于Sublime Text2,同时也适用于Sublime Text3
```
ZYNGA INC.
50 User License
EA7E-811825
927BA117 84C9300F 4A0CCBC4 34A56B44
985E4562 59F2B63B CCCFF92F 0E646B83
0FD6487D 1507AE29 9CC4F9F5 0A6F32E3
0343D868 C18E2CD5 27641A71 25475648
309705B3 E468DDC4 1B766A18 7952D28C
E627DDBA 960A2153 69A2D98A C87C0607
45DC6049 8C04EC29 D18DFA40 442C680B

1342224D 44D90641 33A3B9F2 46AADB8F
```
> 3208版本顶端会显示 `LICENSE UPGRADE REQUIRED`
#### Package Control

在`首选项`里打开`浏览插件目录`，返回上层目录后进入`Installed Packages`文件夹， 复制`Package Control.sublime-package`和`chanel_v3.json`到此目录的下

或使用命令行进行复制操作
```bash
cp "Package Control.sublime-package" ~/.config/sublime-text-3/
cp "chanel_v3.json" ~/.config/sublime-text-3/
```

- package control 配置 chanel_v3

> `Preferences`->`Package Settings`->`Package Control`->`Settings-User` 
增加	`channels` 配置项,配置如下

```
"channels":
[
	"~/.config/sublime-text-3/Installed Packages/channel_v3.json"
]
```
#### 汉化

1. <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>: 打开　｀Package Control｀
1. 输入`pcip`选择`Package Control:Install Package`
1. 输入`chinese`，选择`ZZZZZZZZ-Localization`后安装


## 安装WPS

#### 1. 先将系统自带的LibreOffice的卸载(最小化安装可以略过此步)
```bash	
sudo apt-get purge LibreOffice    ﻿//相较于apt-get remove, 该命令还能清除软件的配置
sudo apt-get autoremove    ﻿//用于清除卸载软件所依赖的包12
```
#### 2. 下载

官网下载WPS和缺失字体
	
WPS:[http://wps-community.org/download.html?vl=a21#download](http://wps-community.org/download.html?vl=a21#download)

缺失字体:[http://wps-community.org/download.html?vl=fonts#download](http://wps-community.org/download.html?vl=fonts#download)

缺失符号(网盘下载):

#### 3. 安装 WPS
	
`sudo dpkg -i wps-office_*.deb`

#### 4. 安装缺失字体及符号

在运行WPS的时候,会提示`Some formula symbols might not be displayed…`,这是由于版权问题,`WPS for Linux`未对此类字体打包安装,需要用于在授权的情况下安装对应的字库.


```bash
# 解压缺失字体和符号压缩包
sudo dpkg -i wps-office-fonts_1.0_all.deb
# 将将字体和符号放到同一个文件夹下 

# 创建一个文件夹存放字库
sudo mkdir -p /usr/share/fonts/wps-office    ﻿ 

# 将字体和符号移动到wps-office目录
sudo cp * /usr/share/fonts/wps-office/
```

##　apt-get 安装清单

```bash
# 网络工具
sudo apt install net-tools

# 安装 Git
sudo apt-get install git

# ssh
sudo apt-get install openssh-server

```
#### Git配置

```bash
# 查看版本
git --version

# 配置
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
git config --list

# 生成秘钥
ssh-keygen -t rsa -C "you@example.com" # 按3个回车,密码为空（免密登录）

# 拷贝 id_rsa.pub 内容到github上进行添加
cat ~/.ssh/id_rsa.pub

# 测试 ssh git@github.com,查看是否出现成功信息
```
#### ssh配置
```bash
# 安装完后查看ssh server是否启动
sudo /etc/init.d/ssh status

# 如果没有启动，使用一下命令启动：
sudo /etc/init.d/ssh start
```
## apt 安装的应用 
 
#### 安装更新pip
	pip install --upgrade pip


#### FTP工具

3、查看虚拟机ip地址

	ifconfig
#### 视频播放器VLC
	sudo apt install vlc
 
#### 主题

首先安装 tweaks，使用该软件统一管理主题中的各个部分

	sudo apt install gnome-tweak-tool 



## purevpn

#### 安装
`sudo dpkg -i purevpn_*amd64.deb`
#### 常用命令
```bash
# how to login
purevpn -login OR purevpn -li

# how to use smart connect 
purevpn -connect OR purevpn -c

# how to connect 
purevpn -connect “Germany” OR purevpn -c “Germany”
purevpn -connect DE OR purevpn -c DE

# how to check connect status
purevpn -status OR purevpn -s

# how to check connection details
purevpn -info OR purevpn -i

# how to check locations
purevpn -location OR purevpn -l

# how to change protocols
purevpn -protocol auto OR purevpn -p auto
purevpn -protocol tcp OR purevpn -p tcp
#To simply view the selected protocol, use the same command with no arguments.
purevpn -protocol

# how to refresh purevpn configuration
purevpn -refresh OR purevpn -r

# how to check your account
purevpn -account purevpn -a

# how to check app version 
purevpn -version purevpn -v

# how to refer for help 
purevpn -help purevpn -h

# how to disconnect 
purevpn -disconnect OR purevpn -d

# how to logout
purevpn -logout OR purevpn -lo

# how to give feedback
purevpn -feedback purevpn -f
```

[https://support.purevpn.com/article-categories/getting-started/linux](https://support.purevpn.com/article-categories/getting-started/linux)

[https://www.purevpn.com/vpn-app-for-linux](https://www.purevpn.com/vpn-app-for-linux)




## Fire fox
### 汉化
- 确定当前浏览器版本
	- 命令行: `firefox --version`
	- `Help`->`About Firefox`
- 安装 xpi 中文插件
	- 将版本号拼入以下 URL
	- http://ftp.mozilla.org/pub/firefox/releases/{fire-fox-version}/linux-x86_64/xpi/zh-CN.xpi
- 地址栏输入 `about:config`
	- 搜索 `intl.locale.requested` 并修改为 `zh-CN`
- 参考链接
	- [https://support.mozilla.org/zh-CN/kb/使用语言包改变Firefox界面语言]

### 同步
- 同步问题参考链接
	- [https://support.mozilla.org/zh-CN/products/firefox/sync-and-save]

### 启动时恢复页面
- 首选项->常规->启动->恢复先前的浏览状态

### 设置主页

### 常用插件
- Octotree ： Code tree for GitHub
- Context Search ： 

### 安装flash
	tar -zxvf flash_player_npapi_linux.x86_64.tar.gz libflashplayer.so

	sudo cp libflashplayer.so /usr/lib/mozilla/plugins/

https://support.mozilla.org/zh-CN/kb/安装 Flash 插件

[test](https://www.baidu.com)