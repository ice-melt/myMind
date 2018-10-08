# ubuntu 18.04版本中，碰到的一些问题

## 目录


### vi 方向键不对	

在终端中依次执行如下两条命令

	sudo apt-get remove vim-common
	sudo apt-get install vim

### 右键菜单无法创建空白文档

在用户主目录里找到**Templates**文件夹

在终端中依次执行如下命令

	sudo gedit 文本文件

保存，退出