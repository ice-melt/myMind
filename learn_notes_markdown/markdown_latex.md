<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>

# Markdown输入数学公式

# 函数、符号及特殊字符

## 正体希腊字母
特征|语法|效果|注释/外部链接
|-|-|-|-| 
大写字母| \Gamma \Delta  \Theta|`$\Gamma\Delta\Theta$`|\Alpha \Beta\Epsilon \Zeta\Eta有道云不支持
大写字母|\Lambda  \Xi  \Pi|`$\Lambda\Xi\Pi$`|\Iota \Kappa \Mu \Nu\Omicron有道云不支持
大写字母| \Sigma \Upsilon \Phi \Psi\Omega|`$\Sigma\Upsilon\Phi\Psi\Omega$`|\Rho\Tau\Chi有道云不支持
小写字母|\alpha \beta \gamma \delta \epsilon \zeta \eta\theta|`$\alpha \beta \gamma \delta \epsilon \zeta \eta\theta$`|
小写字母|\alpha \beta \gamma \delta \epsilon \zeta \eta\theta|`$\iota \kappa\varkappa \lambda \mu \nu \xi \omicron\pi$`
小写字母|\alpha \beta \gamma \delta \epsilon \zeta \eta\theta|`$\rho \sigma \tau \upsilon \phi \chi \psi\omega$`
异体字母|\epsilon\varepsilon|`$\epsilon\varepsilon$`|\Epsilon有道云不支持
异体字母|\Theta\theta\vartheta|`$\Theta\theta\vartheta$`|
异体字母|\kappa\varkappa|`$\kappa\varkappa$`|\Kappa有道云不支持
异体字母|\Pi\pi\varpi|`$\Pi\pi\varpi$`|
异体字母|\rho\varrho|`$\rho\varrho$`|\Rho有道云不支持
异体字母|\Sigma\sigma\varsigma|`$\Sigma\sigma\varsigma$`|
已停用字母|	\digamma|`$\digamma$`

## 括号
功能    |   语法    |	显示
        -|      -   |-
圆括号，小括号|\left( \frac{a}{b} \right)|`$\left( \frac{a}{b} \right)$`
方括号，中括号|\left[ \frac{a}{b} \right]|`$	\left[ \frac{a}{b} \right]$`
花括号，大括号|\left\{ \frac{a}{b} \right\}|`$\left\{ \frac{a}{b} \right\}$`
角括号|\left \langle \frac{a}{b}\right \rangle|`$\left\langle \frac{a}{b} \right \rangle$`
单竖线，绝对值|\left\| \frac{a}{b} \right \| |`$\left| \frac{a}{b} \right|$`	
双竖线，范|\left \\\| \frac{a}{b} \right \\\||`$\left \| \frac{a}{b} \right \|$`
取整函数（Floor function）|\left \lfloor \frac{a}{b} \right \rfloor|`$\left \lfloor \frac{a}{b} \right \rfloor$`
取顶函数（Ceiling function)|\left \lceil \frac{c}{d} \right \rceil|`$\left \lceil \frac{c}{d} \right \rceil$`
斜线与反斜线|\left / \frac{a}{b} \right \backslash|`$\left / \frac{a}{b} \right \backslash $`
单左括号|\left \{ \frac{a}{b} \right .|`$\left \{ \frac{a}{b} \right .$`
单右括号|\left . \frac{a}{b} \right \}|`$\left . \frac{a}{b} \right \}$`
混合括号|\left [ 0,1 \right )|`$\left [ 0,1 \right )$`
混合括号|\left \langle \psi \right \||`$\left \langle \psi \right|$`

-   可以使用 \big, \Big, \bigg, \Bigg 控制括号的大小，比如代码

    `\Bigg ( \bigg [ \Big \{\big\langle \left | \| \frac{a}{b} \| \right | \big \rangle\Big\}\bigg ] \Bigg )`
-   显示
        
    `$\Bigg ( \bigg [ \Big \{\big\langle \left | \| \frac{a}{b} \| \right | \big \rangle\Big\}\bigg ] \Bigg )$`

## 空格
功能|语法|显示|备注
|-|-|-|-|
2个quad空格|\alpha\qquad\beta|`$\alpha\qquad\beta$`|2m
quad空格|\alpha\quad\beta|`$\alpha\quad\beta$`|m
大空格|\alpha\ \beta|`$\alpha\ \beta$`|`$\frac{m}{3}$`
中等空格|\alpha\;\beta|`$\alpha\;\beta$`|`$\frac{2m}{7}$`
小空格|\alpha\,\beta|`$\alpha\,\beta$`|`$\frac{m}{6}$`
没有空格|\alpha\beta|`$\alpha\beta$`|0
紧贴|\alpha\!\beta|`$\alpha\!\beta$`|`$-\frac{m}{6}$`

## 颜色
-   语法
    -   字体颜色︰{\color{色调}表达式}
    -   背景颜色︰{\pagecolor{色调}表达式} ==有道云不支持==
-   **支援色调表**

Colors supported||||
-|-|-|-
`$\color{Apricot}{Apricot}$`|`$\color{Aquamarine}{Aquamarine}$`|`$\color{Bittersweet}{Bittersweet}$`|`$\color{Black}{Black}$`
`$\color{Blue}{Blue}$`|`$\color{BlueGreen}{BlueGreen}$`|`$\color{BlueViolet}{BlueViolet}$`|`$\color{BrickRed}{BrickRed}$`
`$\color{Brown}{Brown}$`|`$\color{BurntOrange}{BurntOrange}$`|`$\color{CadetBlue}{CadetBlue}$`|`$\color{CarnationPink}{CarnationPink}$`
`$\color{Cerulean}{Cerulean}$`|`$\color{CornflowerBlue}{CornflowerBlue}$`|`$\color{Cyan}{Cyan}$`|`$\color{Dandelion}{Dandelion}$`
`$\color{DarkOrchid}{DarkOrchid}$`|`$\color{Emerald}{Emerald}$`|`$\color{ForestGreen}{ForestGreen}$`|`$\color{Fuchsia}{Fuchsia}$`
`$\color{Goldenrod}{Goldenrod}$`|`$\color{Gray}{Gray}$`|`$\color{Green}{Green}$`|`$\color{GreenYellow}{GreenYellow}$`
`$\color{JungleGreen}{JungleGreen}$`|`$\color{Lavender}{Lavender}$`|`$\color{LimeGreen}{LimeGreen}$`|`$\color{Magenta}{Magenta}$`
`$\color{Mahogany}{Mahogany}$`|`$\color{Maroon}{Maroon}$`|`$\color{Melon}{Melon}$`|`$\color{MidnightBlue}{MidnightBlue}$`
`$\color{Mulberry}{Mulberry}$`|`$\color{NavyBlue}{NavyBlue}$`|`$\color{OliveGreen}{OliveGreen}$`|`$\color{Orange}{Orange}$`
`$\color{OrangeRed}{OrangeRed}$`|`$\color{Orchid}{Orchid}$`|`$\color{Peach}{Peach}$`|`$\color{Periwinkle}{Periwinkle}$`
`$\color{PineGreen}{PineGreen}$`|`$\color{Plum}{Plum}$`|`$\color{ProcessBlue}{ProcessBlue}$`|`$\color{Purple}{Purple}$`
`$\color{RawSienna}{RawSienna}$`|`$\color{Red}{Red}$`|`$\color{RedOrange}{RedOrange}$`|`$\color{RedViolet}{RedViolet}$`
`$\color{Rhodamine}{Rhodamine}$`|`$\color{RoyalBlue}{RoyalBlue}$`|`$\color{RoyalPurple}{RoyalPurple}$`|`$\color{RubineRed}{RubineRed}$`
`$\color{Salmon}{Salmon}$`|`$\color{SeaGreen}{SeaGreen}$`|`$\color{Sepia}{Sepia}$`|`$\color{SkyBlue}{SkyBlue}$`
`$\color{SpringGreen}{SpringGreen}$`|`$\color{Tan}{Tan}$`|`$\color{TealBlue}{TealBlue}$`|`$\color{Thistle}{Thistle}$`
`$\color{Turquoise}{Turquoise}$`|`$\color{Violet}{Violet}$`|`$\color{VioletRed}{VioletRed}$`|`$\color{White}{White}$`
`$\color{WildStrawberry}{WildStrawberry}$`|`$\color{Yellow}{Yellow}$`|`$\color{YellowGreen}{YellowGreen}$`|`$\color{YellowOrange}{YellowOrange}$`

`*注︰输入时第一个字母必需以大写输入`
-   eg:
    -   {\color{Blue}x^2}+{\color{Brown}2x} -{\color{OliveGreen}1}

        `${\color{Blue}x^2}+{\color{Brown}2x} - {\color{OliveGreen}1}$`

    -   x_{\color{Red}{1,2}}=\frac{-b\pm\sqrt{{\color{Red}{b^2-4ac}}}}{2a}

        `$x_{\color{Red}{1,2}}=\frac{-b\pm\sqrt{{\color{Red}{b^2-4ac}}}}{2a}$`

## 字体及样式
特征|语法|效果|注释/外部链接
|-|-|-|-| 
**斜粗体**|\boldsymbol||有道云不支持
**黑板粗体**|\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}|`$\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$`|黑板粗体（Blackboardbold）一般用于表示数学和物理学中的向量或集合的符号,{}中只有使用大写拉丁字母才能正常显示，使用小写字母或数字会得到其他符号。
**正粗体**|\mathbf{012…abc…ABC…}|`$\mathbb{012abcABC}$`|花括号{}内只能使用拉丁字母和数字，不能使用希腊字母如\alpha等
*斜体数字*|\mathit{0123456789}|`$\mathit{0123456789}$`
罗马体|\mathrm{012…abc…ABC…}|`$\mathrm{012abcABC}$`|\mbox{}和\operatorname{} 有道云不支持
哥特体|\mathfrak{012…abc…ABC…}|`$\mathfrak{0123456789}$`<br>`$\mathfrak{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$`<br>`$\mathfrak{abcdefghijklmnopqrstuvwxyz}$`|
手写体|\mathcal{ABC…}|`$\mathcal{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$`|手写体仅对大写拉丁字母有效
希伯来字母|\aleph\beth\gimel\daleth|`$\aleph\beth\gimel\daleth$`




## 声调

语法|效果|语法|效果|语法|效果
-|-|-|-|-|-
\bar{x}	|$\bar{x}$|	\acute{\eta}	|`$	\acute{\eta}	$`|	\check{\alpha}	|`$	\check{\alpha}	$`|
\grave{\eta}	|`$	\grave{\eta}	$`|	\breve{a}	|`$	\breve{a}	$`|	\ddot{y}	|`$	\ddot{y}	$`|
\dot{x}	|`$	\dot{x}	$`|	\hat{\alpha}	|`$	\hat{\alpha}	$`|	\tilde{\iota}	|`$	\tilde{\iota}	$`|

## 函数
语法|效果|语法|效果|语法|效果
-|-|-|-|-|-
\sin\theta|`$\sin\theta$`|\cos\theta|`$\cos\theta$`|\tan\theta|`$\tan\theta$`|
\arcsin\frac{L}{r}|`$\arcsin\frac{L}{r}$`|\arccos\frac{T}{r}|`$\arccos\frac{T}{r}$`|\arctan\frac{L}{T}|`$\arctan\frac{L}{T}$`|
\sinh g|`$\sinh g$`|\cosh h|`$\cosh h$`|\tanh i|`$\tanh i$`|
\operatorname{sh}j|`$$`|\operatorname{argsh}k|`$$`|\operatorname{ch}h|`$$`|
\operatorname{argch}l|`$$`|\operatorname{th}i|`$$`|\operatorname{argth}m|`$$`|
k'(x)=\lim\_{\Delta x\to 0}\frac{k(x)-k(x-\Delta x)}{\Deltax} |   `$k'(x)=\lim_{\Delta x\to 0}\frac{k(x)-k(x-\Delta x)}{\Delta x}$`|\limsup S|`$\limsup S$`|\liminf I|`$\liminf I$`|
\max H|`$\max H$`|\min L|`$\min L$`|\inf s|`$\inf s$`|
\sup t|`$\sup t$`|\exp\!t|`$\exp\!t$`|\ln X|`$\ln X$`|
\lg X|`$\lg X$`|\log X|`$\log X$`|\log_\alpha X|`$\log_\alpha X$`|
\ker x|`$\ker x$`|\deg x|`$\deg x$`|\gcd(T,U,V,W,X)|`$\gcd(T,U,V,W,X)$`|
\Pr x|`$\Pr x$`|\det x|`$\det x$`|\hom x|`$\hom x$`|
\arg x|`$\arg x$`|\dim x|`$\dim x$`|\lim_{t\to n}T|`$\lim_{t\to n}T$`|

## 同余
语法|效果|语法|效果
-|-|-|-
\pmod{m}|`$\pmod{m}$`|a \bmod b|`$a \bmod b$`
## 微分
语法|效果|语法|效果|语法|效果
-|-|-|-|-|-
\nabla|`$\nabla$`|\partial x|`$\partial x$`|\mathrm{d}x|`$\mathrm{d}x$`|
\dot x|`$\dot x$`|\ddot y|`$\ddot y$`|||
## 集合
语法|效果|语法|效果|语法|效果|语法|效果|语法|效果
-|-|-|-|-|-|-|-|-|-
\forall|`$\forall$`|\exists|`$\exists$`|\empty|`$$`|\emptyset|`$\emptyset$`|\varnothing|`$\varnothing$`
\in|`$\in$`|\ni|`$\ni$`|\not\in|`$$`|\notin|`$\notin$`|\subset|`$\subset$`
\subseteq|`$\subseteq$`|\supset|`$\supset$`|\supseteq|`$\supseteq$`|\cap|`$\cap$`|\bigcap|`$\bigcap$`
\cup|`$\cup$`|\bigcup|`$\bigcup$`|\biguplus|`$\biguplus$`|\sqsubset|`$\sqsubset$`|\sqsubseteq|`$\sqsubseteq$`
\sqsupset|`$\sqsupset$`|\sqsupseteq|`$\sqsupseteq$`|\sqcap|`$\sqcap$`|\sqcup|`$\sqcup$`|\bigsqcup|`$\bigsqcup$`
## 逻辑
语法|效果|语法|效果|语法|效果|语法|效果
-|-|-|-|-|-|-|-
p|`$p$`|\land|`$\land$`|\wedge|`$\wedge$`|\bigwedge|`$\bigwedge$`
\bar{q} \to p|`$\bar{q} \to p$`|\lor|`$\lor$`|\vee|`$\vee$`|\bigvee|`$\bigvee$`
\lnot|`$\lnot$`|\neg q|`$\neg q$`|\setminus|`$\setminus$`|\smallsetminus|`$\smallsetminus$`
## 根号
语法|效果|语法|效果
-|-|-|-
\sqrt{3}|`$\sqrt{3}$`|\sqrt[n]{3}|`$\sqrt[n]{3}$`|
## 关系符号
语法|效果
-|-
\Delta ABC\sim\Delta XYZ|`$\Delta ABC\sim\Delta XYZ$`
\sqrt{3}\approx1.732050808\ldots|`$\sqrt{3}\approx1.732050808\ldots$`
\simeq|`$\simeq$`
\cong|`$\cong$`
\dot=|`$\dot=$`
\ggg|`$\ggg$`
\gg|`$\gg$`
>|`$>$`
\ge|`$\ge$`
\geqq|`$\geqq$`
=|`$=$`
\leq|`$\leq$`
\leqq|`$\leqq$`
<|`$<$`
\ll|`$\ll$`
\lll|`$\lll$`
(x-y)^2\equiv(-x+y)^2\equiv x^2-2xy+y^2|`$(x-y)^2\equiv(-x+y)^2\equiv x^2-2xy+y^2$`
##question##|question
x\not\equiv N|`$$`
x\ne A|`$x\ne A$`
x\neq C|`$x\neq C$`
t\propto v|`$t\propto v$`
\pm|`$\pm$`
\mp|`$\mp$`

# 几何符号
特征|语法|效果
-|-|-
菱形|\Diamond|`$\Diamond$`
正方形|\Box|`$\Box$`
三角形Delta|\Delta|`$\Delta$`
三角形图型|\triangle|`$\triangle$`
角名|\angle\Alpha\Beta\Gamma|==`$\angle\Gamma\beta\alpha$`==
角度|\sin\!\frac{\pi}{3}=\sin60^\operatorname{\omicron}=\frac{\sqrt{3}}{2}|`$\sin\!\frac{\pi}{3}=\sin60^{\omicron}=\frac{\sqrt{3}}{2}$`
垂直|\perp|`$\perp$`

## 箭头符号
语法|效果|语法|效果|备注
-|-|-|-|-
\leftarrow|`$\leftarrow$`|\rightarrow|`$\rightarrow$`|
\gets|`$\gets$`|\to|`$\to$`|
\hookleftarrow|`$\hookleftarrow$`|\hookrightarrow|`$\hookrightarrow$`|
\longleftarrow|`$\longleftarrow$`|\longrightarrow|`$\longrightarrow$`|
\leftharpoonup|`$\leftharpoonup$`|\rightharpoonup|`$\rightharpoonup$`|
\leftharpoondown|`$\leftharpoondown$`|\rightharpoondown|`$\rightharpoondown$`|
\upharpoonright|`$\upharpoonright$`|\upharpoonleft|`$\upharpoonleft$`|
\downharpoonright|`$\downharpoonright$`|\downharpoonleft|`$\downharpoonleft$`|
\searrow|`$\searrow$`|\swarrow|`$\swarrow$`|
\nearrow|`$\nearrow$`|\nwarrow|`$\nwarrow$`|
\uparrow|`$\uparrow$`|\downarrow|`$\downarrow$`|
\leftrightarrow|`$\leftrightarrow$`|\updownarrow|`$\updownarrow$`|
|\mapsto|`$\mapsto$`|\longmapsto|`$\longmapsto$`|
\Leftarrow|`$\Leftarrow$`|\Rightarrow|`$\Rightarrow$`|
\Longleftarrow|`$\Longleftarrow$`|\Longrightarrow|`$\Longrightarrow$`|
\Uparrow|`$\Uparrow$`|\Downarrow|`$\Downarrow$`|
\Leftrightarrow|`$\Leftrightarrow$`|\Updownarrow|`$\Updownarrow$`|
\Longleftrightarrow (or \iff)|`$\Longleftrightarrow$`|||


## 特殊符号



+----------------------------------------------------+ 
|  本节内容: 三种数学环境, 数学环境中字体和字号, 数  | 
|  学公式中的空格, 上下标, 分式, \displaystyle, 大   | 
|  大小小的括号, 根式, 导数.                         | 
+----------------------------------------------------+ 
  
`$\sin\!\frac{\pi}{3}$`

`$\begin{align}\because\begin{cases}\acute{a}x^2+bx^2+c\gtrless0\gtrless\grave{a}x^2+bx^2+c\\\acute{a}>0>\grave{a}\end{cases}\\\therefore\frac{-b\pm\sqrt{b^2-4\acute{a}c}}{2\acute{a}}{}_\lessgtr^\gtrlessx_\lessgtr^\gtrless\frac{-b\pm\sqrt{b^2-4\grave{a}c}}{2\grave{a}}\end{align}$`


- 上标与下标
>   上标命令是 ^{角标}，下标命令是 _{角标}
(在 LaTeX 中，花括号是用于分组，即花括号内部文本为一组)

- 分式
>   \frac{分子}{分母}

- 根式
>   开平方：\sqrt{表达式}；
>
>   开 n 次方：\sqrt[n]{表达式}

- 求和与积分
>   排版求和符号:    \sum
>
>   积分符号:    \int

- 公式中的空格
>   紧贴 $a\!b$
>
>   没有空格 $ab$
>
>   小空格 a\,b
>
>   中等空格 a\;b
>
>   大空格 a\ b
>
>   quad空格 $a\quad b$
>
>   两个quad空格 $a\qquad b$

- 公式中的定界符
>   $($    %(
>   
>   $)$    %)
>   
>   $[$    %[
>   
>   $]$    %]
>   
>   $\{$    %{
>   
>   $\}$    %}
>   
>   $|$    %|
>   
>   $\|$    %||
>
>   在上述这些定界符之前冠以 \left（修饰左定界符）或 \right（修饰右定界符），可以得到自适应缩放的定界符，它们会根据定界符所包围的公式大小自适应缩放。

- 省略号
>   数学公式中常见的省略号有两种，
>   
>   ldots表示与文本底线对齐的省略号，
>
>   cdots表示与文本中线对齐的省略号。

- 矢量
>   vec{矢量值}


希腊字母
下面的表格用于查询和对比。

|序号 |大写|LaTex代码|小写|LaTex代码|中文名称|
|- |-|-|-|-|-|
|1|A|A|α|alpha|阿尔法|
|2|B|B|β|beta|贝塔|
|3|Γ|Γ|γ|gamma|伽马|
|4|D|D|δ|delta|德尔塔|
|5|E|E|ϵ|epsilon|伊普西隆|
|6|Z|Z|ζ|zeta|泽塔|
|7|H|H|η|eta|伊塔|
|8|Θ|Θ|θ|theta|西塔|
|9|I|I|ι|iota|约塔|
|10|K|K|κ|kappa|卡帕|
|11|Λ|Λ|λ|lambda|兰姆达|
|12|M|M|μ|mu|缪|
|13|N|N|ν|nu|纽|
|14|X|X|ξ|xi|克西|
|15|O|O|ο|omicron|欧米克隆|
|16|P|P|π|pi|派|
|17|R|R|ρ|rho|柔|
|18|Σ|Σ|σ|sigma|西格玛|
|19|T|T|τ|tau|陶|
|20|Υ|Υ|υ|upsilon|宇普西隆|
|21|Φ|Φ|ϕ|phi|弗爱|
|22|X|X|χ|chi|卡|
|23|Ψ|Ψ|ψ|psi|普赛|
|24|Ω|Ω|ω|omega|欧米伽|
|异体|E|E|ε|varepsilon|
|异体|异体|K|K|ϰ|varkappa|
|异体|异体|Θ|Θ|ϑ|vartheta|
|异体|异体|P|P|ϖ|varpi|
|异体|异体|R|R|ϱ|varrho|
|异体|异体|Σ|Σ|ς|varsigma|
|异体|异体|Φ|Φ|φ|varphi|








## 关系运算符
|符号|LaTex代码||符号|LaTex代码|
|-|-|-|-|-|
±  |pm 	||	⨁  |bigoplus 
×  |times 	||	≤  |leq 
÷  |div 	||	≥  |geq 
∣  |mid 	||	≠  |neq 
∤  |nmid 	||	≈  |approx 
⋅  ⋅|cdot 	||	≡  |equiv 
∘  |circ 	||	∑  |sum 
∗  |ast 	||	∏  |prod 
⨀  |bigodot 	||	∐  |coprod
⨂  |bigotimes 	||	
## 集合运算符
|符号|LaTex代码||符号|LaTex代码|
|-|-|-|-|-|
∅  |emptyset 	||	⊇  |bigcap 
∈  |in 	||	⋃  |bigcup 
∉  |notin 	||	⋁  |bigvee 
⊂  |subset 	||	⋀  |bigwedge 
⊃  |supset 	||	⨄  |biguplus 
⊆  |subseteq 	||	⨆  |bigsqcup
⊇  |supseteq 	||	
## 三角运算符
|符号|LaTex代码|
|-|-|
⊥|bot
∠|angle
30∘|30^circ
sin|sin
cos|cos
tan|tan
cot|cot
sec|sec
csc|csc
## 微积分运算符
|符号|LaTex代码|
|-|-|
′|prime
∫|int
∬|iint
∭|iiint
∬∬|iiiint
∮|oint
lim|lim
∞|infty
∇|nabla

## 逻辑运算符
|符号|LaTex代码|
|-|-|
∵|because
∴|therefore
∀|forall
∃|exists
≠|not=
≯|not>
⊄|notsubset

## 戴帽符号
|符号|LaTex代码|
|-|-|
y^|hat{y}
yˇ|check{y}
y˘|breve{y}

## 连线符号
|符号|LaTex代码|
|-|-|
a+b+c+d¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯|overline{a+b+c+d}
a+b+c+d−−−−−−−−−−|underline{a+b+c+d}
a+b+c1.0+d2.0|overbrace{a+underbrace{b+c}_{1.0}+d}^{2.0}

## 箭头符号
|符号|LaTex代码|
|-|-|
↑|uparrow
↓|downarrow
⇑|Uparrow
⇓|Downarrow
→|rightarrow
←|leftarrow
⇒|Rightarrow
⇐|Leftarrow
⟶|longrightarrow
⟵|longleftarrow
⟹|Longrightarrow
⟸|Longleftarrow

## 其它特殊字符：

- 字体种类
> 公式里的字符也有字体的选择，若要对公式的某一部分字符进行字体转换，可以用如下语法格式：
> `{字体标记 需转换的部分字符}`

|字体标记|字体名词|例子|例子效果|
|-|-|-|-|
|rm|罗马体|{rm ABCDE}|ABCDE
|bf|黑体|{bf ABCDE}|ABCDE
|Bbb|黑板粗体字|{Bbb ABCDE}|ABCDE
|sl|倾斜体|{sl ABCDE}|slABCDE
|mit|数学斜体|{mit ABCDE}|ABCDE
|scr|小体大写字母|{scr ABCDE}|ABCDE
|it|意大利体|{it ABCDE}|ABCDE
|cal|花体|{cal ABCDE}|ABCDE
|sf|等线体|{sf ABCDE}|ABCDE
|tt|打字机字体|{tt ABCDE}|ABCDE
|frak|Fraktur字母（一种德国字体）|{frak ABCDE}|ABCDE


---
---
---



`$\Gamma(n) = (n-1)!quadforall ninmathbb N$`

`$ x = \dfrac{-b pm \sqrt{b^2 - 4ac}}{2a} $`

`$x^{y^z}=(1+e^x)^{-2xy^w}$`

`$sideset{^1_2}{^3_4}bigotimes$`

`$left{1 \over 3} \div 4$`

`$\left(1+\frac23x\right)$`

`$(1+\frac23x)$`

`$\vec{a}$`



## Mathematical formula `$y=x^2$`
Inline math: 
`$\tfrac{\tfrac{3}{4}[2-(\tfrac{1}{2})^n]}{1-\tfrac{1}{2}}=s_n$
`.


`$\dfrac{3}{4}$`

`$\oint_c x^3\,dx+4y^2\,dy$`
 

`$ x_{n+1} = \frac{2}{2x_n^2-1}$`

```math
f(x)=sqrt{x}
```

`$\color{#f7acbc}{f7acbc}$`

`$\sum\limits_{i=1}^{n} \int\limits_{0}^{\infty}$`

```math
\lim_x
```