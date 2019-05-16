# Ubuntu 18.04 装机之旅

## 官方推荐 Rufus 制作启动器

官网下载地址：[https://rufus.ie/](https://rufus.ie/)

## ubuntu系统下载

官网下载地址：[http://www.ubuntu.org.cn/download](http://www.ubuntu.org.cn/download)

## ubuntu安装

使用rufus和系统镜像制作完成启动盘

进入BIOS设置U盘优先启动

重装系统

## 系统设置
#### 更新

	sudo apt update
	sudo apt upgrade

#### 设置root用户密码

新装的ubuntu系统,root 用户没有初始密码,使用以下命令进行设置：

	sudo passwd root

#### 开机自动挂载分区

查看硬盘信息
	
	sudo fdisk -l	 

查看硬盘uuid

	sudo blkid

配置开机自动挂载

	sudo gedit /etc/fstab

打开配置文件后,增加配置参考如下:

	UUID=16d0c53f-6c58-40bc-89df-426bfc2420a8 /home/ice-melt/D               ext4    defaults 0       2

配置项共6个参数,分别表示：
1. 设备标识
2. 挂载点(必须是已存在的目录)
3. 文件系统(文件系统可能为ext3,ext4,utfs等)
4. 挂载选项,一般defaults即可
5. 是否备份,0表示不备份,1表示备份
6. 是否开机检查(`fsck`),0不检查,其它大于0的数字检查,数字越小越先检查
#### 修改默认文件夹

###### 1. 用户目录

如果是中文系统,想让`下载`,`音乐`,`视频`等中文目录名称使用英文并改变存储位置(比如空间更大的硬盘上),

设置命令如下：

	sudo gedit ~/.config/user-dirs.dirs

打开配置文件后修改默认路径及名称（将原来的中文目录移除）即可,修改后的文件内容参考如下：

	XDG_DESKTOP_DIR="$HOME/D/desktop"
	XDG_DOWNLOAD_DIR="$HOME/D/download"
	XDG_TEMPLATES_DIR="$HOME/D/template"
	XDG_PUBLICSHARE_DIR="$HOME/D/user"
	XDG_DOCUMENTS_DIR="$HOME/D/document"
	XDG_MUSIC_DIR="$HOME/D/music"
	XDG_PICTURES_DIR="$HOME/D/picture"
	XDG_VIDEOS_DIR="$HOME/D/video"

###### 2. apt-get 缓存目录

	mkdir -p ~/apt-archives
	cd ~/apt-archives
	mkdir partial
	sudo vim /etc/apt/apt.conf

打开配置文件后增加配置如下
	
	dir::cache::archives
