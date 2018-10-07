# ubuntu装机之旅
## 安装Linux
下载地址
## 安装搜狗输入法

## 安装sublime
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -1

sudo apt-get install apt-transport-https1

echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list1

sudo apt-get update1

sudo apt-get install sublime-text1

执行完以上几步就安装成功了！接下来是解决在Ubuntu下sublime不能输入中文的问题！ 
废话也不多说，按顺序执行以下命令！

git clone https://github.com/lyfeyaj/sublime-text-imfix.git1

cd sublime-text-imfix && ./sublime-imfix 
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
