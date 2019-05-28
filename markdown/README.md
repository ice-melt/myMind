# Markdown

> 这里主要记录 GitHub 上支持的 markdown 语法
>
> GitHub的markdown语法在标准的markdown语法基础上做了扩充，称之为`GitHub Flavored Markdown`。  
> 简称`GFM`，GFM在GitHub上有广泛应用，README文件、issues和wiki均支持markdown语法。
> 
> 更专业和基础的介绍可参考[Markdown语法说明（简体中文版）](https://www.appinn.com/markdown/)
****
	
|Author|ice-melt|
|---|---
|E-mail|ice-melt@outlook.com|


****
## 目录

[标题](#标题) [文本](#文本) [横线](#横线) [列表](#列表) [表格](#表格) [图片](#图片) [链接](#链接) [块引用](#块引用) [代码高亮](#代码高亮) [表情](#表情) [diff语法](#diff语法)

---

## 标题

![markdown_titles][markdown_titles] 

## 文本
> 普通文本,直接写就好

这是一段普通的文本

> 单行文本,在一行开头加入1个Tab或者4个空格。

    Hello,MarkDwon。

> 文本块-语法1:在每行文本的开头加入1个Tab或者4个空格。

	Hi,你好
	这里是我的Github项目
	让我们一起学习,一起进步

> 文本块-语法2:使用一对\`\`\`包裹文本：
```
前面有三个`哦，经过markdown渲染后你是看不到的
我是中间的文本
后面也有三个`
```
该语法也可以实现代码高亮，见[代码高亮](#代码高亮)

> 文字高亮：使用一对\`能使行内部分文字高亮。

|语法|效果|
|-|-|
|\`ai\` \`python\` \`linux\` \`人工智能\` |`ai` `python` `linux` `人工智能`|

这种方式适合标注关键字或标注文章的标签
> 换行:  
> 直接回车不能换行，可以在上一行文本后面补两个空格，这样下一行的文本就换行了。  
> 或者就是在两行文本之间增加一个空行。也能实现换行效果，不过这个行间距有点大。

![maarkdown_newlines][maarkdown_newlines]

> 斜体、粗体、删除线

|语法|效果|
|----|-----|
|`*斜体1*` 或 `_斜体2_`|*斜体1* 或 _斜体2_|
|`**粗体1**` 或 `__粗体2__`|**粗体1** 或 __粗体2__|
|`~~删除线~~`|~~删除线~~|
|`***斜粗体1***` 或 `___斜粗体2___`|***斜粗体1*** 或 ___斜粗体2___|
 
> **[Tip]**:斜体、粗体、删除线可混合使用

## 横线
```markdown
***
---
___
```
效果：
***

---

___

> **[Tip]**:“---” 的上下最好各空一行

## 列表

#### 常规的列表语法

```Markdown
Markdown语法：

- 无序列表项目11
- 无序列表项目12 
- 无序列表项目13

* 无序列表项目21
* 无序列表项目22
* 无序列表项目23

1. 有序列表项目31
2. 有序列表项目32
3. 有序列表项目33

- 外层列表项目41
	+ 内层列表项目4101
	+ 内层列表项目4102
	+ 内层列表项目4103
- 外层列表项目42
```
预览效果：

- 无序列表项目11
- 无序列表项目12
- 无序列表项目13
---
* 无序列表项目21
* 无序列表项目22
* 无序列表项目23
---
1. 有序列表项目31
2. 有序列表项目32
3. 有序列表项目33
---
- 外层列表项目41
	+ 内层列表项目4101
	+ 内层列表项目4102
	+ 内层列表项目4103
- 外层列表项目42 

#### 复选框列表

有道云笔记 和 Github 的markdown语法支持这种方式，有些markdown编辑器不支持  
可以使用此功能来标注一个任务列表的各项任务的完成情况。

```
复选框列表语法：
- [x] 10月1号
- [x] 10月2号
- [x] 10月3号
- [ ] 10月4号
- [ ] 10月5号
```
预览效果：

- [x] 10月1号
- [x] 10月2号
- [x] 10月3号
- [ ] 10月4号
- [ ] 10月5号


> **[Tip]**:在GitHub的**issue**中使用该语法是可以实时点击复选框来勾选或解除勾选的，而无需修改issue原文。


## 表格 
```
|title1|title2|title3|
|-|-|-|
|cell01|cell02|cell03|
|cell11|cell12|cell13|
```
效果预览：

|title1|title2|title3|
|-|-|-|
|cell01|cell02|cell03|
|cell11|cell12|cell13|

表格可以指定对齐方式
```
|左对齐|居中|右对齐|
|:-|:-:|-:|
a    | b    | c
d    | e    | f
g    | h    | i
```

效果预览：

|左对齐|居中|右对齐|
|:-|:-:|-:|
a    | b    | c
d    | e    | f
g    | h    | i

> **[Tip]**:表格单元中的内容可以和其他大多数GFM语法配合使用，如`删除线`，`斜体`等效果,或插入`公式`、`链接`、`图片`等  
 

## 图片

基本格式：
```
![alt](URL title)
```
alt和title即对应HTML中的alt和title属性（都可省略）：  
- alt表示图片显示失败时的替换文本  
- title表示鼠标悬停在图片时的显示文本（注意这里要加引号）

URL即图片的url地址，如果引用本仓库中的图片，直接使用**相对路径**就可了，如果引用其他github仓库中的图片要注意格式，即：`仓库地址/raw/分支名/图片路径`，如：
```
https://github.com/ice-melt/picture-set/raw/master/loading001.gif
```

| |语法|效果|
|---|---|----
|1|`![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")`|![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")
|2|`![][loading]`|![][loading]

>在文末有loading的定义,相关链接都放在文章末尾显得比较清爽也方便复用，查找 和 修改
```
[loading]:https://github.com/ice-melt/picture-set/raw/master/loading001.gif
```

## 链接

#### 链接外部URL

| |语法|效果|
|---|----|-----|
|1|`[我的站点](http://ice-melt.top "夕兮曦兮")`|[我的站点](http://ice-melt.top "夕兮曦兮")|
|2|`[百度][baidu]`|[百度][baidu]|

#### 链接本仓库里的URL

|语法|效果|
|----|-----|
|`[Markdown 参考资料](markdown_material.md)`|[Markdown 参考资料](markdown_material.md)|


#### 图片链接
给图片加链接的本质是混合图片显示语法和普通的链接语法。普通的链接中[ ]内部是链接要显示的文本，而图片链接[ ]里面则是要显示的图片。  
直接混合两种语法当然可以，但是十分啰嗦，为此我们可以使用URL标识符的形式。

|#|语法|效果|
|---|----|:---:|
|1|`[![cnblogs-logo]](http://www.cnblogs.com/ICE_melt/ "博客园")`|[![cnblogs-logo]](http://www.cnblogs.com/ICE_melt/ "博客园")|
|2|`[![csdn-logo]][csdn]`|[![csdn-logo]][csdn]|


#### 锚点
在markdown中每一个标题都是一个锚点，和HTML的锚点（`#`）类似`(有些markdown预览不支持此语法)`。

|语法|效果|
|---|---|
|`[回到顶部](#markdown)`|[回到顶部](#markdown)|

> **[Tip]**:标题中的英文字母都被转化为**小写字母**了。  
> 以前GitHub对中文支持的不好，所以中文标题不能正确识别为锚点，但是现在已经没问题啦！


## 块引用

在每行的最前面加上 `>` ：

```
>  舜发于畎亩之中，傅说举于版筑之间，胶鬲举于鱼盐之中，管夷吾举于士，孙叔敖举于海，百里奚举于市。  
>  故天将降大任于是人也，必先苦其心志，劳其筋骨，饿其体肤，空乏其身，行拂乱其所为，所以动心忍性，  
> 曾益其所不能。
>  
> 人恒过，然后能改，困于心衡于虑而后作，征于色发于声而后喻。入则无法家拂士，出则无敌国外患者，  
> 国恒亡，然后知生于忧患而死于安乐也。
```   
>  舜发于畎亩之中，傅说举于版筑之间，胶鬲举于鱼盐之中，管夷吾举于士，孙叔敖举于海，百里奚举于市。  
>  故天将降大任于是人也，必先苦其心志，劳其筋骨，饿其体肤，空乏其身，行拂乱其所为，所以动心忍性，  
> 曾益其所不能。
>  
> 人恒过，然后能改，困于心衡于虑而后作，征于色发于声而后喻。入则无法家拂士，出则无敌国外患者，  
> 国恒亡，然后知生于忧患而死于安乐也。

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 `>`：

```
> 陕西省
>> 西安市
>>> 雁塔区
```
> 陕西省
>> 西安市
>>> 雁塔区

---

> **[Tip]**:  
> 引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等；  
> 可以偷懒只在整个段落的第一行最前面加上 `>` ：

# 代码高亮

语法

```
	在三个反引号后面加上编程语言的名字，另起一行开始写代码，最后一行再加上三个反引号。
	```Java
	public static void main(String[]args){} //Java
	```
	```c
	int main(int argc, char *argv[]) //C
	```
	```Bash
	echo "hello GitHub" #Bash
	```
	```javascript
	document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
	```
	```cpp
	string &operator+(const string& A,const string& B) //cpp
	```
```

效果预览：

```Java
public static void main(String[]args){} //Java
```
```c
int main(int argc, char *argv[]) //C
```
```Bash
echo "hello GitHub" #Bash
```
```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```
```cpp
string &operator+(const string& A,const string& B) //cpp
```

# 表情

Github的Markdown语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。

比如`:blush:`，可以显示:blush:。

具体每一个表情的符号码，可以查询GitHub的官方网页[http://www.emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com)。

# diff语法 

版本控制的系统中都少不了diff的功能，即展示一个文件内容的增加与删除。
GFM中可以显示的展示diff效果。使用绿色表示新增，红色表示删除。

语法:  
```
	其语法与代码高亮类似，只是在三个反引号后面写diff，
	并且其内容中，以 `+ `开头表示新增，`- `开头表示删除。
	```diff
	+ 鸟宿池边树，僧敲月下门
	- 鸟宿池边树，僧推月下门
	```
```
效果:

```diff
+ 鸟宿池边树，僧敲月下门
- 鸟宿池边树，僧推月下门
```



--------------------------------
[markdown_titles]:https://github.com/ice-melt/picture-set/raw/master/mymind/markdown_001_titles.png
[maarkdown_newlines]:https://github.com/ice-melt/picture-set/raw/master/mymind/markdown_002_newlines.png
[loading]:https://github.com/ice-melt/picture-set/raw/master/loading001.gif
[baidu]:https://www.baidu.com "百度一下 你就知道"
[csdn]:https://blog.csdn.net/xxliu_csdn "我的博客"
[baidu-logo]:http://www.baidu.com/img/bdlogo.gif "百度logo"
[cnblogs-logo]:https://github.com/ice-melt/picture-set/raw/master/icons/cnblogs.gif "博客园"
[csdn-logo]:https://github.com/ice-melt/picture-set/raw/master/icons/csdn.png "我的CSDN博客"

