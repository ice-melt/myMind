# Ubuntu 18.04 安装 sublime3
## 安装 sublime3
	# install the GPG key
	wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -

	# Ensure apt is set up to work with https sources
	sudo apt-get install apt-transport-https

	echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

	sudo apt-get update

	sudo apt-get install sublime-text

## 解决在Ubuntu下sublime不能输入中文的问题
	git clone https://github.com/lyfeyaj/sublime-text-imfix.git1

	cd sublime-text-imfix && ./sublime-imfix 

## Package Control
- 官方网站: [https://packagecontrol.io](https://packagecontrol.io/installation)
- ctrl+\` 后输入以下命令安装 package control
	
	`import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)`

## 破解
- 选择 help-->enter license
- 授权码
	```
	----- BEGIN LICENSE -----
	sgbteam
	Single User License
	EA7E-1153259
	8891CBB9 F1513E4F 1A3405C1 A865D53F
	115F202E 7B91AB2D 0D2A40ED 352B269B
	76E84F0B CD69BFC7 59F2DFEF E267328F
	215652A3 E88F9D8F 4C38E3BA 5B2DAAE4
	969624E7 DC9CD4D5 717FB40C 1B9738CF
	20B3C4F1 E917B5B3 87C38D9C ACCE7DD8
	5F7EF854 86B9743C FADC04AA FB0DA5C0
	F913BE58 42FEA319 F954EFDD AE881E0B
	------ END LICENSE ------
	```
- 出现以下信息说明授权码过期，需要重新寻找授权码
	`That license key has been invalidated, due to being shared.
	Please email sales@sublimetext.com to get your license key reissued.`

## 禁止自动更新
- 设置 Preferences -> Settings-User
- 添加 "update_check": false
---

## 汉化
- Ctrl+Shift+P 输入 pcip 选择 `Package Control：Install Package`
- 安装 `ChineseLocalizations`
- 使用方式
	```
	help--请使用主菜单的 帮助/Language 子菜单来切换语言。 目前支持 简体中文 繁体中文 日本語 德语 法语 俄语等。 
	要换回英语不需要卸载本插件，请直接从菜单切换英文。
	```

集合插件
SideBarEnhancements 侧栏右键功能增强
auto-save 自动保存
 

Alignment： 自动对齐代码
SublimeLinter 提示编写代码中存在的不规范和错误的写法
Sublime CodeIntel代码提示和补全
Bracket Highlighter代码匹配

ConvertToUTF8，GBK编码兼容
Emmet让编写代码变得简单
HTML-CSS-JS Prettify HTML/CSS/JS/Vue等代码格式化
AutoFileName提示文件路径，快速输入文件名
GitGutter提示代码中插入、修改、删除的地方
PackageResourceViewer，插件修改必备
PackageResourceViewer，插件修改必备

by roustar31、zd423 - 基于 Sublime Text 3 官方版进行修改汉化；
破解并集成正版密钥已注册版，去自动检测升级提示；
整合GBK插件支持简体中文整合多款主题及细节优化；
参考清风流音的汉化，清除个人信息； - 可自选添加/删除右键菜单项；

1、基于官方版进行全网最完美汉化，基本上没什么英文了。
2、已默认注册软件无需购买，有钱的程序员可以支持正版。
3、去除程序自动检测升级，即无更新选项也没有升级提示。
4、调整字体大小自动换行等细节，以符合大众的使用习惯。
5、修正中文输入法鼠标跟随问题，深度整合GBK编码插件。
6、修改多处菜单选项和配置文件，使其更加实用更人性化。


- Emmet

Emmet绝对的节省时间。您可以轻松快速地编写HTML。
- BracketHighlighter

--- 该插件提供行数列高亮的各种配对的语法符号。（愚人码头注：就是将配对的括号等显示在行数列上
- Colorpicker

--- 使用一个取色器改变颜色
使用方法: ctrl + shift + c
- DocBlockr

--- 一个真正简单的方式来轻松地创建许多语言包括JavaScript，PHP和CoffeeScript的文档块。只要在函数的上面输入/**，按Tab就可以了。DocBlockr会观察函数需要的变量名和类型，并创建文档块。
- SidebarEnhancements

--- 扩展文件树右键功能
- CSSComb

--- 用来给CSS属性进行排序的格式化

注：因为Csscomb的快捷键是shift+ctrl+c，可能与其他快捷键冲突
你可以去Preferences-->插件设置-->CssComb-->key-Bindings-Defallut设置
- ColorHighlighter

--- 它可以展示你所选择的颜色代码（像“#FFFFFF”, “rgb(255,255,255)”, “white”）的真正颜色。同时它还包含一个颜色选择器让你可以方便地更改颜色。
--- 使用：快捷键Windows: ctrl+shift+w
- Trailing spaces

--- 功能：检测并一键去除代码中多余的空格
使用：安装插件并重启，即可自动提示多余空格。一键删除多余空格：CTRL+SHITF+T（需配置）
快捷键配置：在Preferences / Key Bindings – User加上代码（数组内）{ "keys": ["ctrl+shift+t"], "command": "delete_trailing_spaces" },
- auto-save

--- 功能：自动保存文件
使用：默认是不会自动保存，按快捷键Ctrl+Shift+S开启。
快捷键配置方法：首选项-快捷键设置，在数组内添加{ "keys": ["ctrl+shift+s"], "command": "auto_save" },如需自动启用，首选项-插件-auto-save---settings-usre粘帖一下配置
{
"auto_save_on_modified": true,
"auto_save_delay_in_seconds": 10,
"auto_save_all_files": true,
"auto_save_current_file": "",
"auto_save_backup": false,
"auto_save_backup_suffix": "autosave"
}
- view in browser

--- 功能：通过默认浏览器打开文件
使用：快捷键配置方法：首选项-快捷键设置，在数组内添加快捷键：{ "keys": ["f12"], "command": "open_in_browser" },
- autoprefixer

--- 功能：CSS添加私有前缀
简介：CSS还未标准化，所以要给各大浏览器一个前缀以解决兼容问题
使用：快捷键配置方法：首选项-快捷键设置，在数组内添加{ "keys": ["ctrl+shift+enter"], "command": "autoprefixer" },
快捷键：ctrl+shift+enter
- CSS Extended Completions

--- 功能：关联CSS文件，智能提示css文件中的类名，非常好用
- JavaScript Completions

--- 功能：支持javascript原生语法提示
- jQuery

--- 功能：jQ函数提示
简介：快捷输入jQ函数，是偷懒的好方法
- AutoFileName

--- 功能：快捷输入文件名
简介：自动完成文件名的输入，如图片选取
使用：输入”/”即可看到相对于本项目文件夹的其他文件
- HTML-CSS-JS Prettify

--- 功能：快捷输入文件名
简介: 编辑HTML, CSS, JS时，经常会出现缩进不对，代码行不对其的情况。装了这个插件之后，只要按下 Ctrl+Shift+h (Windows), Command+Shift+h (Mac), 你的文档就会被整理干净。
注: 需要配置node文件路径 HTML-CSS-JS Prettify > plugin Options