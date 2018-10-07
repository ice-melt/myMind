# sublime markdown

## 编辑

## 预览

可以选择 Markdown Preview 或 MarkdownLivePreview .

#### MarkdownLivePreview

 可以实现实时预览, 在首选项->Package Setting里修改MarkdownLivePreview的user配置文件,设置在打开时同步预览
	
	"markdown_live_preview_on_open": true

#### Markdown Preview

设置快捷键让在浏览器中预览,在首选项->快捷键设置里添加

	{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"} },

#### OmniMarkupPreviewer
可以实现在浏览器中实时预览,双显示屏有较好的体验,

安装后在首选项->Package Setting里修改OmniMarkupPreviewer的setting-user添加

	{
	    "renderer_options-MarkdownRenderer": {
	        "extensions": ["tables", "fenced_code", "codehilite"]
	    }
	}

在要预览的文件里右键->Preview markup in browser 或者按快捷键ctrl+alt+o就可以在浏览器里预览了.
感觉html的样式不如Markdown Preview好看,但是胜在可以实时预览,比较方便.
另外可以修改扩展的配置文件,将预览地址改为局域网下的地址,这样如果你有Pad之类的话,就可以用pad访问预览地址,用电脑编写

	{
	    "renderer_options-MarkdownRenderer": {
	        "extensions": ["tables", "fenced_code", "codehilite"]
	    },
	    "server_host": "192.168.2.137"
	}