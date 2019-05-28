# Ubuntu 18.04 常用软件安装

## 前言

又一次重新安装Ubuntu，想把装机过程的过程记录下来方便后续学习印证


## 安装搜狗输入法

#### fcitx框架

搜狗拼音需要fcitx框架,18.04可以直接在软件中心搜索下载

下载完成后打开`语言支持`将`键盘输入法系统`修改为`fcitx`,并`应用到整个系统`

#### 安装
```bash
# 先安装依赖
# sudo apt install libopencc1 fcitx-libs fcitx-libs-qt fonts-droid-fallback
# 有可能需要根据安装 sougoupinyin 的报错提示信息安装缺失的依赖
sudo apt install libopencc2 libfcitx-qt0 fcitx-libs libqtwebkit4

# 安装wps
sudo dpkg -i sogoupinyin_*.deb
```

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

## Pycharm
#### 安装
```bash
# 解压
tar -zxvf pycharm-professional-2019.1.1.tar.gz
# copy到/opt目录下
sudo cp pycharm-professional-2019.1.1 /opt/pycharm
# 安装
cd pycharm
./configure
```
#### 破解
```bash
56ZS5PQ1RF-eyJsaWNlbnNlSWQiOiI1NlpTNVBRMVJGIiwibGljZW5zZWVOYW1lIjoi5q2j54mI5o6I5p2DIC4iLCJhc3NpZ25lZU5hbWUiOiIiLCJhc3NpZ25lZUVtYWlsIjoiIiwibGljZW5zZVJlc3RyaWN0aW9uIjoiRm9yIGVkdWNhdGlvbmFsIHVzZSBvbmx5IiwiY2hlY2tDb25jdXJyZW50VXNlIjpmYWxzZSwicHJvZHVjdHMiOlt7ImNvZGUiOiJJSSIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9LHsiY29kZSI6IkFDIiwicGFpZFVwVG8iOiIyMDIwLTAzLTEwIn0seyJjb2RlIjoiRFBOIiwicGFpZFVwVG8iOiIyMDIwLTAzLTEwIn0seyJjb2RlIjoiUFMiLCJwYWlkVXBUbyI6IjIwMjAtMDMtMTAifSx7ImNvZGUiOiJHTyIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9LHsiY29kZSI6IkRNIiwicGFpZFVwVG8iOiIyMDIwLTAzLTEwIn0seyJjb2RlIjoiQ0wiLCJwYWlkVXBUbyI6IjIwMjAtMDMtMTAifSx7ImNvZGUiOiJSUzAiLCJwYWlkVXBUbyI6IjIwMjAtMDMtMTAifSx7ImNvZGUiOiJSQyIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9LHsiY29kZSI6IlJEIiwicGFpZFVwVG8iOiIyMDIwLTAzLTEwIn0seyJjb2RlIjoiUEMiLCJwYWlkVXBUbyI6IjIwMjAtMDMtMTAifSx7ImNvZGUiOiJSTSIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9LHsiY29kZSI6IldTIiwicGFpZFVwVG8iOiIyMDIwLTAzLTEwIn0seyJjb2RlIjoiREIiLCJwYWlkVXBUbyI6IjIwMjAtMDMtMTAifSx7ImNvZGUiOiJEQyIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9LHsiY29kZSI6IlJTVSIsInBhaWRVcFRvIjoiMjAyMC0wMy0xMCJ9XSwiaGFzaCI6IjEyMjkxNDk4LzAiLCJncmFjZVBlcmlvZERheXMiOjAsImF1dG9Qcm9sb25nYXRlZCI6ZmFsc2UsImlzQXV0b1Byb2xvbmdhdGVkIjpmYWxzZX0=-SYSsDcgL1WJmHnsiGaHUWbaZLPIe2oI3QiIneDtaIbh/SZOqu63G7RGudSjf3ssPb1zxroMti/bK9II1ugHz/nTjw31Uah7D0HqeaCO7Zc0q9BeHysiWmBZ+8bABs5vr25GgIa5pO7CJhL7RitXQbWpAajrMBAeZ2En3wCgNwT6D6hNmiMlhXsWgwkw2OKnyHZ2dl8yEL+oV5SW14t7bdjYGKQrYjSd4+2zc4FnaX88yLnGNO9B3U6G+BuM37pxS5MjHrkHqMTK8W3I66mIj6IB6dYXD5nvKKO1OZREBAr6LV0BqRYSbuJKFhZ8nd6YDG20GvW6leimv0rHVBFmA0w==-MIIElTCCAn2gAwIBAgIBCTANBgkqhkiG9w0BAQsFADAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBMB4XDTE4MTEwMTEyMjk0NloXDTIwMTEwMjEyMjk0NlowaDELMAkGA1UEBhMCQ1oxDjAMBgNVBAgMBU51c2xlMQ8wDQYDVQQHDAZQcmFndWUxGTAXBgNVBAoMEEpldEJyYWlucyBzLnIuby4xHTAbBgNVBAMMFHByb2QzeS1mcm9tLTIwMTgxMTAxMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxcQkq+zdxlR2mmRYBPzGbUNdMN6OaXiXzxIWtMEkrJMO/5oUfQJbLLuMSMK0QHFmaI37WShyxZcfRCidwXjot4zmNBKnlyHodDij/78TmVqFl8nOeD5+07B8VEaIu7c3E1N+e1doC6wht4I4+IEmtsPAdoaj5WCQVQbrI8KeT8M9VcBIWX7fD0fhexfg3ZRt0xqwMcXGNp3DdJHiO0rCdU+Itv7EmtnSVq9jBG1usMSFvMowR25mju2JcPFp1+I4ZI+FqgR8gyG8oiNDyNEoAbsR3lOpI7grUYSvkB/xVy/VoklPCK2h0f0GJxFjnye8NT1PAywoyl7RmiAVRE/EKwIDAQABo4GZMIGWMAkGA1UdEwQCMAAwHQYDVR0OBBYEFGEpG9oZGcfLMGNBkY7SgHiMGgTcMEgGA1UdIwRBMD+AFKOetkhnQhI2Qb1t4Lm0oFKLl/GzoRykGjAYMRYwFAYDVQQDDA1KZXRQcm9maWxlIENBggkA0myxg7KDeeEwEwYDVR0lBAwwCgYIKwYBBQUHAwEwCwYDVR0PBAQDAgWgMA0GCSqGSIb3DQEBCwUAA4ICAQAF8uc+YJOHHwOFcPzmbjcxNDuGoOUIP+2h1R75Lecswb7ru2LWWSUMtXVKQzChLNPn/72W0k+oI056tgiwuG7M49LXp4zQVlQnFmWU1wwGvVhq5R63Rpjx1zjGUhcXgayu7+9zMUW596Lbomsg8qVve6euqsrFicYkIIuUu4zYPndJwfe0YkS5nY72SHnNdbPhEnN8wcB2Kz+OIG0lih3yz5EqFhld03bGp222ZQCIghCTVL6QBNadGsiN/lWLl4JdR3lJkZzlpFdiHijoVRdWeSWqM4y0t23c92HXKrgppoSV18XMxrWVdoSM3nuMHwxGhFyde05OdDtLpCv+jlWf5REAHHA201pAU6bJSZINyHDUTB+Beo28rRXSwSh3OUIvYwKNVeoBY+KwOJ7WnuTCUq1meE6GkKc4D/cXmgpOyW/1SmBz3XjVIi/zprZ0zf3qH5mkphtg6ksjKgKjmx1cXfZAAX6wcDBNaCL+Ortep1Dh8xDUbqbBVNBL4jbiL3i3xsfNiyJgaZ5sX7i8tmStEpLbPwvHcByuf59qJhV/bZOl8KqJBETCDJcY6O2aqhTUy+9x93ThKs1GKrRPePrWPluud7ttlgtRveit/pcBrnQcXOl1rHq7ByB8CFAxNotRUYL9IF5n3wJOgkPojMy6jetQA5Ogc8Sm7RG6vg1yow==
```
#### 设置桌面图标,并固定到收藏夹
```bash
sudo touch /usr/share/applications/pycharm.desktop
sudo gedit /usr/share/applications/pycharm.desktop

# 复制以下内容到 pycharm.desktop
[Desktop Entry]
 
Version=1.0
 
Type=Application
 
Name=Pycharm
 
Icon=/opt/pycharm/bin/pycharm.png
 
Exec=/opt/pycharm/bin/pycharm.sh
 
MimeType=application/x-py;
 
Name[en_US]=pycharm
```
保存退出后,即可在应用程序中找到 `pycharm` 图标，右击保存到收藏夹

#### 修改host
```bash
sudo gedit /etc/hosts
# 文件末尾添加
0.0.0.0 account.jetbrains.com
0.0.0.0 www.jetbrains.com
```

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


## 
seahorse


## nodejs
sudo apt install nodejs
sudo apt install npm
npm：
npm config set registry https://registry.npm.taobao.org
npm config get registry

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


## ubuntu 美化

https://www.cnblogs.com/lishanlei/p/9090404.html

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