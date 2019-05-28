# Ubuntu 18.04 装机之旅

## 官方推荐 Rufus 制作启动器

官网下载地址：[https://rufus.ie/](https://rufus.ie/)

### ubuntu系统下载

官网下载地址：[http://www.ubuntu.org.cn/download](http://www.ubuntu.org.cn/download)

## ubuntu安装

使用rufus和系统镜像制作完成启动盘

进入BIOS设置U盘优先启动

重装系统

## 系统设置

#### 查看系统版本 
```bash
cat /proc/version
lsb_release -a
```
#### 更新
```bash
sudo apt update
sudo apt upgrade
```
#### 设置root用户密码

新装的ubuntu系统,root 用户没有初始密码,使用以下命令进行设置：

```bash	
sudo passwd root
# 出现 passwd: password updated successfully 信息表示成功
```

> 备注：
>
> `#`符号 是系统用户 root
>
> `$`符号 是你创建的用户 没指定权限！ 

#### 设置用户sudo时不用输入密码
```bash
sudo gedit /etc/sudoers
# %sudo	ALL=(ALL:ALL) ALL:ALL
# 修改为
# %sudo	ALL=(ALL:ALL) NOPASSWD:ALL
```

#### 开机自动挂载分区

查看硬盘信息
	
`sudo fdisk -l	`

查看硬盘uuid

`sudo blkid`

配置开机自动挂载

`sudo gedit /etc/fstab`

打开配置文件后,增加配置参考如下:

`UUID=${uuid} ${mount-path}  ${file-system}  defaults 0       2`

配置项共6个参数,分别表示：

1. ${uuid} 设备标识,eg:`16d0c53f-6c58-40bc-89df-426bfc2420a8`
2. ${mount-path} 挂载点(必须是已存在的目录),eg:`/home/ice-melt/dist`
3. ${file-system} 文件系统(文件系统可能为ext3,ext4,utfs等),eg:`ext4`
4. 挂载选项,一般 `defaults` 即可
5. 是否备份,`0`表示不备份,`1`表示备份
6. 是否开机检查(`fsck`),0不检查,其它大于0的数字检查,数字越小越先检查

#### 修改默认文件夹

###### 1. 用户目录

如果是中文系统,想让`下载`,`音乐`,`视频`等中文目录名称使用英文并改变存储位置(比如空间更大的硬盘上),

设置命令如下：

`sudo gedit ~/.config/user-dirs.dirs`

打开配置文件后修改默认路径及名称（将原来的中文目录移除）即可,修改后的文件内容参考如下：

```
	XDG_DESKTOP_DIR="$HOME/disk/desktop"
	XDG_DOWNLOAD_DIR="$HOME/disk/download"
	XDG_TEMPLATES_DIR="$HOME/disk/template"
	XDG_PUBLICSHARE_DIR="$HOME/disk/user"
	XDG_DOCUMENTS_DIR="$HOME/disk/document"
	XDG_MUSIC_DIR="$HOME/disk/music"
	XDG_PICTURES_DIR="$HOME/disk/picture"
	XDG_VIDEOS_DIR="$HOME/disk/video"
```

###### 2. apt-get 缓存目录

```bash
mkdir -p ~/apt-archives
cd ~/apt-archives
mkdir partial
sudo vim /etc/apt/apt.conf
```
打开配置文件后增加配置如下
	
`dir::cache::archives`

#### vi 方向键不对	

在终端中依次执行如下两条命令

```bash
sudo apt-get remove vim-common
sudo apt-get install vim
```
#### 右键菜单无法创建空白文档

在用户主目录里找到**`Templates`**文件夹

在终端中依次执行如下命令

`sudo gedit 文本文件`

保存，退出