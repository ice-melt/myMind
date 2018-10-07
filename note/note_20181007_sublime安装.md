# Ubuntu 18.04 安装 sublime3
## 安装 sublime3
	# install the GPG key
	wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -

	# Ensure apt is set up to work with https sources
	sudo apt-get install apt-transport-https

	echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

	sudo apt-get update

	sudo apt-get install sublime-text

## Package Control
- 官方网站: [https://packagecontrol.io](https://packagecontrol.io/installation)
- ctrl+\` 后输入以下命令安装 package control
	```
	import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
	```

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
	```
	That license key has been invalidated, due to being shared.
	Please email sales@sublimetext.com to get your license key reissued.
	```

## 禁止自动更新
- 设置 Preferences -> Settings-User
- 添加 "update_check": false

---

# issues

## 解决在Ubuntu下sublime不能输入中文的问题
	git clone https://github.com/lyfeyaj/sublime-text-imfix.git1

	cd sublime-text-imfix && ./sublime-imfix 

---

# sublime plugins list

插件名称|功能简述
|-|-|
SideBarEnhancements|侧栏右键功能增强
auto-save|自动保存
Alignment|自动对齐代码
SublimeLinter|提示编写代码中存在的不规范和错误的写法
Sublime CodeIntel|代码提示和补全
Bracket Highlighter|代码匹配
ConvertToUTF8|GBK编码兼容
Emmet|让编写代码变得简单
HTML-CSS-JS Prettify|HTML/CSS/JS/Vue等代码格式化
AutoFileName|提示文件路径，快速输入文件名
GitGutter|提示代码中插入、修改、删除的地方
PackageResourceViewer|插件修改必备 

---

# sublime theme list

## [Boxy Theme][boxy]

### Boxy Yesterday
	"theme": "Boxy Yesterday.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Yesterday.tmTheme",
### Boxy Tomorrow
	"theme": "Boxy Tomorrow.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Tomorrow.tmTheme",
### Boxy Ocean
	"theme": "Boxy Ocean.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Ocean.tmTheme",
### Boxy Monokai
	"theme": "Boxy Monokai.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Monokai.tmTheme",
### Boxy Solarized Dark
	"theme": "Boxy Solarized Dark.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Solarized Dark.tmTheme",
### Boxy Solarized Light
	"theme": "Boxy Solarized Light.sublime-theme",
	"color_scheme": "Packages/Boxy Theme/schemes/Boxy Solarized Light.tmTheme",

## Material Theme

[boxy](https://github.com/ihodev/sublime-boxy)