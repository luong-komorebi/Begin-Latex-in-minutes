[English](./readme.md) ·
中文 ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# 学习 LaTeX 从现在开始

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**译者前言：** *本人尽量按照原作者原意翻译，但水平有限，如有翻译不妥之处，欢迎指正。如果您喜欢本文，欢迎分享给更多人看到。*

(**Chinese translator's Acknowledgement:** *I try to translate this guide as the original meaning of the author.But because of the level limited, if the translation is inappropriate, welcome to modified or added.If you like this guide, please share to more people.*)

**前言:** *以下所写均来自于作者的大学经历以及阅读了很多材料之后的感悟。作者不是这方面的专家，仅仅是一个对这门语言有极大热情的学生。任何人都可以在问题分区（issue）中开启新的讨论，或者对需要修改或添加内容申请修改（pull request ）。如果你认为作者的工作是有价值的，欢迎进行[捐赠](#donation)。*

### 目录
* [LaTeX 是什么？](#latex-是什么)
* [为什么要用 LaTeX？](#为什么要用-latex)
* [安装 LaTeX](#安装-latex)
* [第一个 LaTeX 文件](#第一个-latex-文件)
* [深入理解 Hello World](#深入理解-hello-world)
* [使用多种语言](#使用多种语言)
* [列表](#列表)
* [段落与章节](#段落与章节)
* [插入目录](#插入目录)
* [脚注](#脚注)
* [什么是宏包](#什么是宏包)
* [表格](#表格)
* [添加图像](#添加图像)
* [在 LaTeX 中插入代码](#在-latex-中插入代码)
* [分割为多个 LaTeX 文件](#分割为多个-latex-文件)
* [更多工具](#更多工具)

## LaTeX 是什么？

LaTeX 是一种用于进行高质量排版的文档处理系统。LaTeX 读作 «Lah-tech» 或者 «Lay-tech» (和 «blech» 的韵母一样)。它被广泛的用于排版大中型科学技术文献，除此之外，它几乎能用于排版任何形式的出版物。

## 为什么要用 LaTeX？

* LaTeX 是免费、多平台的。
* LaTeX 只是一种文本文件(可以用任何文本编辑器打开)，并且能很容易的转换成 PDF。
* LaTeX 的内容和格式是分离的。一旦设定好风格，就能专注于内容。
* 与 MS Word 相比，工作流程更快。
* LaTeX 被广泛的用于科学主题中。
* LaTeX 是排版数学公式的最佳选择。

> LaTeX 并不是没有缺点，但它仍然值得学习。

## 安装 LaTeX

你将需要以下几个软件：

1. *LaTeX 的发行版：*
我使用 windows 版的 [MiKTeX](https://miktex.org/about)。
2. *LaTeX 编辑器：*
我使用 [TeXMaker](http://www.xm1math.net/texmaker/) 来编辑文件，当然使用任何一个文本编辑器均可以创建并修改 LaTeX 文件。
1. *PDF 查看器：* (可选)
任何 PDF 查看器均可，取决于你的喜好。

另外，你需要选择一个[编译器](#更多工具)。大多数编辑人员的默认编译器是 pdfLaTeX ，但如果你想在你的系统中使用 Unicode 或 TTF / OTF 字体，你需要 LuaLaTeX 。

或者你可以选择在线软件，比如 [ShareLaTeX](https://www.sharelatex.com/)，
你可以在[更多工具](#更多工具)一节中看到更多选择。

## 第一个 LaTeX 文件

让我们用 **LaTeX** 中编写传统的 **Hello World**。
如果你装好了 **TexMaker** ，首先创建一个后缀名为 `.tex` 的新文件。然后在文件里敲入如下代码并运行快速构建( quick build )。对于其他 LaTeX 编辑器，也应该很容易遵循相同的过程。


```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

在 TexMaker 中完成后的结果应该和下图一样：
![](http://i.imgur.com/ZuD5N6U.png)

## 深入理解 Hello World

:eyes: 仔细看你的第一个 LaTeX 文件你会发现：
* 第一行告诉解释器：你正在使用的纸张大小为 A4，文档样式为**文章(article)**。你将来可能还会使用到**报告(report)**、 **书籍(book)** 等样式。
* 正文内容被包裹在 **\begin{document}** 和 **\end{document}** 中。这就是文件的核心，就像 *java* 和 *C++* 中的 `main()` 一样，没有它们，就无法正确的渲染文档。
* 在 begin 和 end 之间就是你自己要写的内容（在样例中就是 `Hello World !` ）。
* **百分号**(%)是 LaTeX 的注释符号，之后的内容会被忽略。

#### :zap: 注意 :zap:

* 回顾这三部分：**\begin{document}**、**\end{document}**、**\documentclass[a4paper]{article}**，你大概注意到了这种样式，它们被称为**排版命令(Typesetting Commands)**(通常以 “\” 开头)和**参数(arguments)**(放在一对花括号 “{}” 之间)。 LaTeX 是由这些命令驱动的普通格式的文本。
* 如果你按照该指南的步骤进行操作，一切都会很顺畅。但将来你可能会遇到一些错误，**不要惊慌**，错误报告写的非常明白且容易理解。如果你不能解决这些问题，谷歌等搜索工具会是你的好伙伴。
* 一些特殊字符**在 LaTeX 中被预定义了。如果你想得到正确的输出，需要在这些字符之前加上反斜杠(\\)。**

![](http://i.imgur.com/9d0bXHH.png)

## 使用多种语言

**有些语言不能开箱即用。为了在 TeX 中使用其他语言，你有这些选择：**

#### :white_check_mark: 第一种方法 :white_check_mark:

第一种方法是导入["宏包(packages)"](#什么是宏包)(你会在之后学到)。因为默认的编译器 pdfLaTeX 限制为 256 个字符并且有很多编码问题。例如：

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

这里我们使用了 `usepackage[T5]{fontenc}` 和 `usepackage[utf8]{inputenc}` 宏包。这种方法非常容易理解，用宏包将字体导入字体编码器并正确显示你的内容。如果你正在使用 TexMaker ，那么代码显示的结果将会如下图所示：

![](http://i.imgur.com/UQEewYi.png)

对比没有导入宏包 :package: 的情况：

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: 这有一个处理中日韩字符的小技巧，使用 `usepackage{CJKutf8}` ， `\begin{CJK}{UTF8}` 和 `\end{CJK}` 非常便利。这里有一个日语版本 :jp: :
```tex
\documentclass[a4paper]{article}
\usepackage{CJKutf8}

\begin{document}

\begin{CJK}{UTF8}{min}
この記事を読んでいただきありがとうございます。
%Thank you for reading this article.
\end{CJK} 

\end{document}
```

就像吃 :sushi: 和 :bento: 一样简单: 

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: 第二种方法 :white_check_mark:
另一种方法是切换你的 TeX 编译器到 [LuaLaTeX](#更多工具) (or [XeLaTeX](#更多工具))。使用 `fontspec` 和 `polyglossia`, 然后你就可以直接使用 Unicode :

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

默认字体(Latin Modern)不支持全部字符，但是你可以通过取消 `\setmainfont` 行的注释，使用系统上安装的绝大多数字体（完全支持 TTF 和 OTF 字体）。

## 列表

:straight_ruler: 保持你的文件结构清晰是很重要的，因此，让我们从项目列表开始学起。
两个常用的项目列表类型是**有序**和**无序**列表。LaTeX 可以轻松的处理两种列表：
* 无序列表
无序列表只需要 **"itemize"**。(双关语)
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```  
* 有序列表
有序列表需要我们通过 **"enumerate"** 枚举他们。(双关语)
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

以下是两种类型列表的输出样式：

![](http://i.imgur.com/jzN4RWm.png)

## 段落与章节

:blue_book: 我们用 `\section` 表示一节，用 `\paragraph` 表示一个段落。
:orange_book: 你还可以用 `\subsection` 添加小节，用 `\subparagraph` 添加小段落。

![](http://i.imgur.com/qKbZYnG.png)

## 插入目录

:metal: 通过插入 `\tableofcontents` 在目录中显示节和小节是非常方便的。

例如：

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **小技巧**: 你可以使用 `\newpage`命令来创建新的一页。

## 脚注

使用脚注 + 标签 + 参考来做各种各样的脚注，就像制作饼馅一样简单。例如：

```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down:你能看见它吗？:point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **小技巧**: 你可以使用 `\newline` 来换行。

## 什么是宏包

LaTeX 默认提供许多函数，但在某些情况下，宏包就可以派上用场。你可以使用 `\usepackage` :package: 来导入宏包：

这有一个使用两个宏包来显示数学公式的例子:

![](http://i.imgur.com/050nrfh.png)

宏包甚至可以用来绘制电路图:

![](http://i.imgur.com/If4lbLA.png)

:construction: 如果你有其他需求，你可以用谷歌搜索你需要的宏包。例如: amsmath 含有大量数学格式拓展并被广泛用于数学学科，circuitikz 用于电路设计等等。。。这篇通用的指南无法将这些知识全部覆盖。

## 表格

一个实用的例子:

```tex
\begin{table}[h!]
  \centering
  \caption{Caption for the table.}
  \label{tab:table1}
  \begin{tabular}{l|c||r}
    1 & 2 & 3\\
    \hline
    a & b & c\\
  \end{tabular}
\end{table}
```

:star2: 这是它渲染完的样式 :star2: :

![](http://i.imgur.com/XbZJJ2E.png)

现在让我们再回顾一下 :eyes: :

* 对于表格，首先我们需要一个以 `\begin{table}` 开头和  `\end{table}` 结尾的表格环境。
* 你将在图像章节学习有关 h! 内容。它可以让你通过 `\centering` 命令使表格保持在页面中央。
* Caption 用来写描述性的文字。 Label 用来进行标记。你将在图像章节继续学习这些内容。
* Tabular 是最重要的部分。表格环境中往往需要包含一个 tabular 环境。
  - 我们用 `{l|c||r}` 来控制表格的内部样式。这里我们发现：
    * l , c , r 分别表示单元格内容是左对齐、居中、或右对齐的。
    * 竖线 | 和 || 实际上是控制表格列中垂直线的边框格式。
  - 1 & 2 & 3 => 1 2 3 是单元格的内容， & 用来分隔每行中的单元格内容。
  -  `\hline` 实际上是用来添加一个水平线，用于分隔两行。

:bangbang: **小技巧** 你可以使用一个名叫 booktabs 的宏包 :package: 来获得更好的视觉效果。

## 添加图像

若想在 LaTeX 文件中添加图像，你需要使用图形环境和 graphicx 宏包。使用  `\usepackage{graphicx}` 和

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **小技巧**: 用 [width=\linewidth] 将图像缩放到文档的宽度。 如果你想浮动图像，那么你需要用一个特定的值给开头赋值。fig 用来在后面被引用，所以需要仔细命名。

```tex
\begin{figure}[h!]
```

:passport_control: 合法的值有:

* h (here) - 在当前位置(same location)
* t (top) - 页首(top of page)
* b (bottom) - 页尾(bottom of page)
* p (page) - 另起一页(on an extra page)
* ! (override) - 在指定位置(will force the specified location)

下图是图像呈现的样式:

![](http://i.imgur.com/ysY9MOb.png)

## 在 LaTeX 中插入代码

#### :white_check_mark: 第一种方法 :white_check_mark:

对程序员和开发人员至关重要的一个方面是如何专业地将代码插入到文档中。

在 LaTeX 中,这个过程简单且专业，我们只需使用一些预定义的标记来包裹这些代码，然后就可以了。

例如:

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello world!

\begin{verbatim}
#include <iostream>

int main()
{
	std::cout << "hello world!\n";
	return 0;
}
\end{verbatim}

\end{document}
```

:speech_balloon: **LaTeX 支持这些语言的语法** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

如你所见，通过使用 **{verbatim}** 包裹，你可以轻松插入代码而不用担心语法的格式化问题。下图是它渲染的结果，干净、专业、开箱即用:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: 第二种方法 :white_check_mark: :white_check_mark:

这种方法让你有更多的选择，比如:插入代码**内联**,使用**自定义样式**的代码，选择**特定代码语言**,**从**同一目录(the same directory)中的其他文件**导入代码**...使用这个方法时，你无需使用 **{verbatim}** ，而需要包含名叫  **listings** 的宏包 :package: 。

思考下面这个样例：
```tex
\documentclass[a4paper]{article}

\usepackage{listings}
\usepackage{color}

\lstdefinestyle{mystyle}{
keywordstyle=\color{magenta},
backgroundcolor=\color{yellow},
commentstyle=\color{green},
basicstyle=\footnotesize,
}
\lstset{style=mystyle}

\begin{document}


Hello world!

\begin{lstlisting}[language=Python]

print "Hello World!"

\end{lstlisting}

\lstinputlisting[language=C++]{hello.cpp}

Lorem ipsum dolor sit amet \lstinline{print "Hello World"} , consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


\end{document}

```
从这个例子中，你会发现:

1. 插入的代码块，从 `\begin{lstlisting}` 开始，以 `\end{lstlisting}` 结束。
2. 你可以使用 `lstinputlisiting{name_of_file}` 来从同一目录(the same directory)下导入另一个文件的代码。
3. 用 `[language=C++]` 来指定使用的语言。
4. 想插入内联代码需要使用 `\lstinline`。
5. 想应用自定义样式，需要使用 `\usepackage{color}` 然后用你自己的主题定义列表(请看下面的代码)。你可以使用自己的风格修改许多内容，但你需要阅读文档以获取正确的属性名称。
6. 感兴趣？？查看[更多内容](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings)。

以下是 TexMaker 中的代码如何编译的:

![](http://i.imgur.com/XwwDJNo.png)

## 分割为多个 LaTeX 文件

当我们使用 LaTeX 时，我们可能因为一个文档太长而无法处理。因此，我们应该分割文件，使其内容可以轻松的处理。

让我们看这个例子:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

这只是一个普通的 LaTeX 文件，让我们用 `\input` 关键字来将文件分成两个部分：

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

\input{second_file}

\end{document}
```


```tex
% second_file.tex
Hello Latex, This is my second part.
```

现在，主文件看起来有些不同，当文件被更好地组织了。在 TexMaker 中的结果如下：

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **小技巧** : 为了具有可读，清晰，便于维护的目的，强烈建议你将主文件系统性的，分级的，科学的分开。不要没有任何理由的分开，否则你会在以后感到困惑。

## 更多工具

#### 版本(Distributions)

* [TeX Live](https://www.tug.org/texlive/) 适用于所有平台（包括 Windows、Linux 和基于 Unix 的系统）。
* [MiKTeX](https://miktex.org/about) 适用于 Windows。
* [MacTeX](https://tug.org/mactex/) 适用于 macOS。
* [Overleaf](https://www.overleaf.com/) — 一个在线合作的编辑器。
* [StackEdit](https://stackedit.io/) - 在浏览器中的 markdown 编辑器。

#### LaTeX 编辑器

* [TeXMaker](http://www.xm1math.net/texmaker/) 跨平台的 LaTeX 编辑器。
* [TeXStudio](http://www.texstudio.org/) 增强 TeXMaker 的更多功能( An enhanced fork of TeXMaker with more features)。
* TeXShop and TeXworks (最简编辑器, TeX Live 自带)

#### LaTeX 编译器

大多数编译器有选项来改变默认编译器。这有一个例子:

![](http://i.imgur.com/FbNUiL7.png)

## 哦耶 ！！

:tada: 恭喜你完成了本指南。这是所有你需要了解的关于 LaTeX 的基本知识。 :hammer: 
如果你有兴趣了解更多的 LaTeX 知识，点击[这里](http://www.latex-project.org/help/documentation/)或者可以在网上搜寻你需要的内容。

## 版权许可

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
每个人都被允许修改或分发本版权文件，并且只要更改文件名，就允许更改它(Changing it is allowed as long as the name is changed)。复制，分发和修改的条款和条件：你可以用来做任何你想做的。


<div id='donation'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

您所在国家买一瓶啤酒所花的钱可以在作者那里买一顿饭。
