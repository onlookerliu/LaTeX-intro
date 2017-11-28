---
presentation:
  enableSpeakerNotes: true
  width: 960
  height: 700

toc:
  depth_from: 1
  depth_to: 6
  ordered: false

output: pdf_document
---

<!-- slide -->
# LaTeX: 优雅高效的写作方式

present by **Kai Liu**
held by *Graduate Student Union*

<p style="font-size: 20px;">Nov 29, 2017, 7:30-9:00pm</p>
<p style="font-size: 20px;">Meeting Room, School of Mathematical Sciences</p>

<!-- slide -->
## 写在LaTeX之前...

<!-- slide -->
### 为什么要用 LaTeX?

- 纯文本 <!-- .element: class="fragment" data-fragment-index="1" -->
- 跨平台 <!-- .element: class="fragment" data-fragment-index="2" -->
- 高效 <!-- .element: class="fragment" data-fragment-index="3" -->
- 优雅 <!-- .element: class="fragment" data-fragment-index="4" -->
- 强大 <!-- .element: class="fragment" data-fragment-index="5" -->

<!-- slide -->
### 什么样的人适合LaTeX?

1. 科研工作者

2. 高质量排版用户

3. 厌倦 MS Office 的同学 :wink: <!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide -->
### LaTeX 简史

@import "https://upload.wikimedia.org/wikipedia/commons/4/4f/KnuthAtOpenContentAlliance.jpg" (width: 60%)
- TeX 的发明者
- Stanford CS系终身教授
- 1974年图灵奖得主
- The Art of Computer Programming
- ...

<!-- slide -->
### 安装 LaTeX

- Windows和Linux平台建议使用[TeXLive](http://www.tug.org/texlive/)，目前已更新至2017发行版

- Mac建议使用[MacTeX](https://www.tug.org/mactex/)，对中文支持较好

- 尚未安装完成的可以使用云编译，[sharelatex](https://cn.sharelatex.com/project)是个不错的选择 <!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide -->
### LaTeX的工作流程

- Input: *.tex源文件* (纯文本)
- Output: *pdf成品文档*

</br>

1. 编写.tex文件 <!-- .element: class="fragment" data-fragment-index="1" -->
2. 使用latex引擎编译 <!-- .element: class="fragment" data-fragment-index="2" -->
3. 生成PDF文档并发布 <!-- .element: class="fragment" data-fragment-index="3" -->

<!-- slide -->
### 第一个文档 :punch:

<!-- slide -->
在 TeXWorks 编辑器中输入如下
```LaTeX
\documentclass{article}
\begin{document}
\begin{center}
Welcome to \\
\LaTeX
\end{center}
\end{document}
```

点击`排版`按钮，或打开命令行输入 
```bash
xelatex 1.tex
```
就可以得到一个全新的PDF文档

<!-- slide -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex1.png"

<!-- slide -->
## 动手写LaTeX :satisfied:

<!-- slide -->

### LaTeX 文档的基本构成

<!-- slide vertical=true -->
- 导言区
    - 文类定义
    - 宏包引用
    - 页面版式
    - 命令和其他信息
- 正文
    - document环境
    - 部分、章、节，段落等
- 注释
    - 解释和分割

<!-- slide vertical=true -->
顾名思义，`\documentclass` 就是文类。

- 常见的英文文类有article，report，book等。不同文类有细微差异，aricle最常用。

- ctexart 文类相比 article，日期变成了中文表达，而且行间距自动增加了，更适应汉字的排版。 <!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide vertical=true -->

很多精致的文档需要~~红~~宏包的协助来编写。

- ctex宏包支持文档中文化，且提供了中文对应的文类

- 宏包需要被事先下载

<!-- slide vertical=true -->

```LaTeX
\documentclass{ctexart}

\title{Introduction to \LaTeX}
\author{Kai Liu}
\date{\today}
\usepackage{lipsum}

\begin{document}
\maketitle
\lipsum[1-2]
\end{document}
```

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex2.png" (width: 100%)

<!-- slide vertical=true -->
LaTeX 中的命令以\开始

- \title <!-- .element: class="fragment" data-fragment-index="1" -->
- \author <!-- .element: class="fragment" data-fragment-index="1" -->
- \date <!-- .element: class="fragment" data-fragment-index="1" -->
- \usepackage 
  lipsum 宏包用来生成随机文章 <!-- .element: class="fragment" data-fragment-index="2" -->
- \maketitle 
  放在**正文区！** <!-- .element: class="fragment" data-fragment-index="3" -->
- \centering
  **环境**，成对出现，用处最广。 <!-- .element: class="fragment" data-fragment-index="4" -->

<!-- slide -->

### 字体与字号 :yum:

<!-- slide -->
字号
- <p style="font-size: 8px">\tiny</p>
- <p style="font-size: 10px">\scriptsize</p>
- <p style="font-size: 12px">\footnotesize</p>
- <p style="font-size: 14px">\small<p/>
- <p style="font-size: 16px">\normalsize<p/>
- <p style="font-size: 18px">\large<p/>
- <p style="font-size: 20px">\Large<p/>
- <p style="font-size: 22px">\LARGE<p/>
- <p style="font-size: 24px">\huge<p/>
- <p style="font-size: 26px">\HUGE<p/>

<!-- slide -->
**注意区别!**

```LaTeX
There are smaller words and {\Large larger words} %只是部分字体放大
```

```LaTeX
\documentclass[c5size]{ctexart} %全文都是五号字体
```

<!-- slide -->
ctex 宏包提供了字号指定命令，用法相同。

- 小五：\zihao{-5}
- 六号：\zihao{6}
- 初号：\zihao{0}
- 小四：\zihao{-4}

<!-- slide -->
字体
1. 字体族
    - 罗马 roman
    - 无衬线 sans serif
    - 打字机 typewriter
2. 字体形状
    - 直立 upshape
    - 意大利 italic shape
    - 倾斜 slanted shape

<!-- slide -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex3.png"

<!-- slide -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex4.png"

- 着重强调一般用`\emph`命令，而非斜体 <!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide -->
### 常用排版效果 :star:

<!-- slide -->
1. 脚注 
```
\footnote{脚注内容}
```

2. 强调 
```LaTeX
\emph{强调内容}
```

3. 修改行距 
```LaTeX
\linespread{倍数}
```

4. 靠左、靠右、居中 
```LaTeX
   \raggedright \raggedleft \centering
```

<!-- slide -->
常用罗列环境

@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex5.png"
<!-- 1. 计数列表
```LaTeX
\begin{enumerate}
\item blabla
\item blabla
\end{enumerate}
```
- 无序列表
```LaTeX
\begin{itemize}
\item 2
\item 1
\end{itemize}
``` -->

<!-- slide vertical=true -->
### 结构化你的文档 :file_folder:

1. section       节 <!-- .element: class="fragment" data-fragment-index="1" -->
2. subsection    小节 <!-- .element: class="fragment" data-fragment-index="2" -->
3. subsubsection 小小节 <!-- .element: class="fragment" data-fragment-index="3" -->
4. paragraph     无编号 <!-- .element: class="fragment" data-fragment-index="4" -->
5. subparagraph  无编号 <!-- .element: class="fragment" data-fragment-index="5" -->

<!-- slide -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex6.png"

<!-- slide vertical=true -->
### :point_up_2: 标签与交叉引用 :point_down:

1. 给需要引用的章节、公式等进行标记 \label{标签名称} <!-- .element: class="fragment" data-fragment-index="1" -->

2. 在指定位置用 \ref{标签名称} 进行引用 <!-- .element: class="fragment" data-fragment-index="2" -->

- 引擎每次编译从头到尾读一遍，但一遍不能确定编号，故需要二次编译。<!-- .element: class="fragment" data-fragment-index="3" -->

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex7.png"

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex8.png"

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex9.png"

<!-- slide -->
### 获取帮助 :orange_book:

<!-- slide -->
- texlive 安装宏包后自带文档说明
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/texdoc.png"
- 英文文档比较全，注意时效性。<!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide -->
### 制作目录

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex10.png"

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex11.png"

<!-- slide -->
### 插入数学公式 :sunglasses:

<!-- slide vertical=true -->
1. 行内公式
```LaTeX
The equation $E=mc^2$ is embedded in words.
```

2. 行间公式
```LaTeX
\[
    E = mc^2
\]
```

<!-- slide vertical=true -->
上^下_标 
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex12.png"

<!-- slide vertical=true -->
squre root & fractions
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex13.png"

<!-- slide vertical=true -->
运算符
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex14.png"

<!-- slide vertical=true -->
定界符
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex15.png"

<!-- slide vertical=true -->
省略号
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex16.png"

<!-- slide vertical=true -->
矩阵
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex17.png"

<!-- slide vertical=true -->
行内小矩阵
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex18.png"

<!-- slide vertical=true -->
不对齐的多行公式
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex19.png"

<!-- slide vertical=true -->
对齐的多行公式
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex20.png"

<!-- slide vertical=true -->
公式组 (单独编号)
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex21.png"

<!-- slide vertical=true -->
公式组 (按块编号)
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/add21.png"

<!-- slide vertical=true -->
**永远不要使用eqnarray环境**
- [eqnarray 是糟糕的](https://faculty.math.illinois.edu/~hildebr/tex/displays.html)
- [eqnarray 是有害的](http://texblog.net/latex-archive/maths/eqnarray-align-environment/)
- [eqnarray 是恼人的](http://www.tex.ac.uk/cgi-bin/texfaq2html?label=eqnarray)
- [eqnarray 是邪恶的](http://www.tug.org/pracjourn/2006-4/madsen/)

<!-- slide vertical=true -->
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/eqnarray.png"

<!-- slide vertical=true -->
分情况的公式组
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex22.png"

<!-- slide -->
### 插入图片与表格

<!-- slide vertical=true -->
插入图片
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex23.png"

<!-- slide vertical=true -->
插入表格
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex24.png"

<!-- slide vertical=true -->
控制浮动体
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex25.png"

<!-- slide vertical=true -->
给图表加标题与标签
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex26.png"

<!-- slide -->
### 版面设置

<!-- slide vertical=true -->
页面尺寸 (geometry包)
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex27.png"

<!-- slide vertical=true -->
使用 \pagestyle 命令可以调用三种默认的页面风格：

- plain 
  只有页底中央的页码 <!-- .element: class="fragment" data-fragment-index="1" -->
- empty
  啥也没有 <!-- .element: class="fragment" data-fragment-index="2" -->
- headings
  把章节的标题写在页眉处，同时有页码 <!-- .element: class="fragment" data-fragment-index="3" -->

- 默认 :point_down: <!-- .element: class="fragment" data-fragment-index="4" -->
```LaTeX
\pagestyle{headings}
```


<!-- slide vertical=true -->
页眉页脚 (fancyhdr包)
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex28.png"

<!-- slide vertical=true -->
行间距 (setspace包)
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex29.png"

<!-- slide vertical=true -->
段间距 \addtolength\parskip{2em}
@import "http://oye4atjxc.bkt.clouddn.com/LaTeX/intro/ex30.png"

<!-- slide -->
### 模板的使用 :ledger:

1. 有一定**基础**再去尝试 <!-- .element: class="fragment" data-fragment-index="1" -->

2. 使用**文档齐全**的模板 <!-- .element: class="fragment" data-fragment-index="2" -->

3. 注意模板的**时效** <!-- .element: class="fragment" data-fragment-index="3" -->

4. **仔细阅读 README** <!-- .element: class="fragment" data-fragment-index="4" -->

5. [LaTeX Studio](http://www.latexstudio.net/) <!-- .element: class="fragment" data-fragment-index="5" -->

<!-- slide -->
### 问题处理 :grey_question:

<!-- slide vertical=true -->

1. 24K纯新手，建议先读完一本[入门读物](https://book.douban.com/subject/24703731/)，了解基本的知识 <!-- .element: class="fragment" data-fragment-index="1" -->

2. 无论如何，先读[文档](http://www.ctex.org/OnlineDocuments)！绝大部分问题都是文档可以解决的 <!-- .element: class="fragment" data-fragment-index="2" -->

3. 利用 Google 等[搜索引擎](https://tex.stackexchange.com/)你的问题 <!-- .element: class="fragment" data-fragment-index="3" -->

4. 在各个[论坛社区](http://bbs.ctex.org/forum.php?showoldetails=yes)或者 LaTeX 交流群里聪明地提出你的问题 <!-- .element: class="fragment" data-fragment-index="4" -->

<!-- slide -->
### 引擎的选择 

- 排版引擎先进程
  TeX-pdfTeX-XeTeX-LuaTeX <!-- .element: class="fragment" data-fragment-index="1" -->

- 生成 pdf 文件需要使用引擎对应软件
  pdflatex-xelatex-lualatex <!-- .element: class="fragment" data-fragment-index="2" -->

- 发行版软件合集
  CTeX-MikTeX-TeXLive <!-- .element: class="fragment" data-fragment-index="3" -->

<!-- slide -->
### 编辑器选择 :new_moon_with_face:

@import "https://cloud.githubusercontent.com/assets/1908863/14398210/0e408954-fda8-11e5-9eb4-562d7c0ca431.gif" <!-- .element: class="fragment" data-fragment-index="1" -->

<!-- slide vertical=true -->

1. 编辑器一定要打开行号，打开行号！<!-- .element: class="fragment" data-fragment-index="1" -->

2. 多使用编辑器的替换查找功能！<!-- .element: class="fragment" data-fragment-index="2" -->

3. 选择一款适合自己的字体，百看不腻有木有！<!-- .element: class="fragment" data-fragment-index="3" -->

4. 如果能有代码自动补全，那再好不过。<!-- .element: class="fragment" data-fragment-index="4" -->

5. 没有代码补全的最好要有代码高亮。<!-- .element: class="fragment" data-fragment-index="5" -->

<!-- slide -->
### 代码风格 

1. 多使用注释！<!-- .element: class="fragment" data-fragment-index="1" -->

2. 空行永远不要嫌少！<!-- .element: class="fragment" data-fragment-index="2" -->

3. 能简则简，避免长命令以及命令过挤！<!-- .element: class="fragment" data-fragment-index="3" -->

4. 多使用自定义命令！<!-- .element: class="fragment" data-fragment-index="4" -->

5. 学习模板中高手的代码！<!-- .element: class="fragment" data-fragment-index="5" -->








