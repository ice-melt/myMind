# Ubuntu 18.04 装机之旅
## 前言

又一次重新安装Ubuntu，想把装机过程的过程记录下来方便后续学习印证

## 安装Linux

下载地址

## 安装搜狗输入法

## 安装sublime

![这里应该插入链接](test)

## 安装WPS
- LibreOffice的卸载
	sudo apt-get purge LibreOffice    ﻿//相较于apt-get remove, 该命令还能清除软件的配置
	sudo apt-get autoremove    ﻿//用于清除卸载软件所依赖的包12
- WPS官网
	http://wps-community.org/download.html?vl=a21#download 		//WPS 下载
	http://wps-community.org/download.html?vl=fonts#download 	//字体 下载
- 安装 WPS
	sudo dpkg -i wps-office_10.1.0.5707~a21_amd64.deb
- 安装字体
	sudo dpkg -i wps-office-fonts_1.0_all.deb
	sudo mkdir -p /usr/share/fonts/wps-office    ﻿//创建一个文件夹存放字库1
- issue
	- 在运行WPS的时候,会提示”Some formula symbols might not be displayed…”,这是由于版权问题,WPS for Linux未对此类字体打包安装,需要用于在授权的情况下安装对应的字库.
 
## 配置git

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

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


