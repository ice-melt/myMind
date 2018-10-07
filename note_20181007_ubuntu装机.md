# Ubuntu 18.04 装机之旅
## 前言

又一次重新安装Ubuntu，想把装机过程的过程记录下来方便后续学习印证

## 安装Linux

下载地址

## 安装搜狗输入法

## 安装sublime

![这里应该插入链接](test)

## 安装WPS
=========================================================================================
1、去WPS官网选在合适的版本下载：http://wps-community.org/download.html?vl=a21#download
2、下载好之后，进入安装包所在目录，执行安装：sudo dpkg -i  wps-office_10.1.0.5707~a21_amd64.deb
3、如果需要安装字体，还是在官网下载：http://wps-community.org/download.html?vl=fonts#download
4、进入安装包目录，执行安装：sudo dpkg -i wps-office-fonts_1.0_all.deb
---------------------
LibreOffice的卸载
sudo apt-get purge LibreOffice    ﻿//相较于apt-get remove, 该命令还能清除软件的配置
sudo apt-get autoremove    ﻿//用于清除卸载软件所依赖的包12
WPS的安装 
sudo dpkg -i wps-office.deb 
在运行WPS的时候,会提示”Some formula symbols might not be displayed…”,这是由于版权问题,WPS for Linux未对此类字体打包安装,需要用于在授权的情况下安装对应的字库.
sudo mkdir -p /usr/share/fonts/wps-office    ﻿//创建一个文件夹存放字库1
将得到的字库文件复制到上述文件夹后解压,运行指令
sudo fc-cache -vf 
=========================================================================================
## 配置git
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"






[test](https://www.baidu.com)