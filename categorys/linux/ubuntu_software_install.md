# Ubuntu 18.04 常用软件安装

## 前言

又一次重新安装Ubuntu，想把装机过程的过程记录下来方便后续学习印证


## 安装搜狗输入法
搜狗拼音需要fcitx框架,18.04可以直接在软件中心搜索下载

下载完成后打开`语言支持`将`键盘输入法系统`修改为`fcitx`

搜狗输入法安装

	sudo dpkg -i sogoupinyin_*.deb

安装搜狗输入法有可能遇到的问题:

1. 不管什么问题,正常安装后可先尝试重启系统后查看问题是否解决

2. Ubuntu18.04搜狗拼音输入法候选栏无法显示中文（英文乱码）

	输入中文时，若候选栏显示英文乱码、无法显示中文，如下图所示，可按如下方式处理：

		cd ~/.config
		rm -rf SogouPY* sogou*
		
## 安装sublime

![这里应该插入链接](test)

## 安装WPS

#### 1. 先将系统自带的LibreOffice的卸载(最小化安装可以略过此步)
	
	sudo apt-get purge LibreOffice    ﻿//相较于apt-get remove, 该命令还能清除软件的配置
	sudo apt-get autoremove    ﻿//用于清除卸载软件所依赖的包12

#### 2. 下载

官网下载WPS和缺失字体
	
[WPS](http://wps-community.org/download.html?vl=a21#download)
[缺失字体](http://wps-community.org/download.html?vl=fonts#download)

网盘:[]()

[缺失符号(网盘下载)]

#### 3. 安装 WPS
	
	sudo dpkg -i wps-office_*.deb

#### 4. 安装缺失字体及符号

- issue
	- 在运行WPS的时候,会提示”Some formula symbols might not be displayed…”,这是由于版权问题,WPS for Linux未对此类字体打包安装,需要用于在授权的情况下安装对应的字库.


- 安装缺失字体及符号
```bash
	# 解压缺失字体和符号压缩包
	sudo dpkg -i wps-office-fonts_1.0_all.deb
	# 将将字体和符号放到同一个文件夹下 

	# 创建一个文件夹存放字库
	sudo mkdir -p /usr/share/fonts/wps-office    ﻿ 

	# 将字体和符号移动到wps-office目录

	sudo cp * /usr/share/fonts/wps-office/
```
 
## Git
- 安装
	
	sudo apt-get install git
	git --version

- 配置
```bash
	git config --global user.email "you@example.com"
	git config --global user.name "Your Name"
	git config --list
```
- 生成秘钥
```bash
	ssh-keygen -t rsa -C "you@example.com"
	# 按3个回车,密码为空（免密登录）
	cd ~/.ssh
	# github：拷贝 id_rsa.pub 内容到github上进行添加
	# 		测试 ssh git@github.com,查看是否出现成功信息
	# ssh：ssh-add 文件名
```


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

## Required software


