# ubuntu 18.04 必要的软件

目录
## 安装更新pip
	pip install --upgrade pip

## 网络工具
	sudo apt install net-tools
## FTP工具
1、安装ssh server:

	sudo apt-get install openssh-server

2、安装完后查看ssh server是否启动

	sudo /etc/init.d/ssh status

如果没有启动，使用一下命令启动：

	sudo /etc/init.d/ssh start

3、查看虚拟机ip地址

	ifconfig

 