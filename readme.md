English ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# Begin LaTeX in minutes

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Acknowledgement:** _Everything written below is from my own experience in college and after reading various materials. I am neither a professional nor expert, but a student who has great passion for the language. Anyone can open a discussion in the issue section, or a pull request in case something should be modified or added. If you consider my work valuable, a [donation](#donation) is much appreciated._

### Table of Contents

- [What is LaTeX?](#what-is-latex)
- [Why use LaTeX?](#why-use-latex)
- [Set up for LaTeX](#set-up-for-latex)
- [First LaTeX file](#first-latex-file)
- [A deeper look](#a-deeper-look)
- [Multilingual usage](#multilingual-usage)
- [Lists](#lists)
- [Paragraph and section](#paragraph-and-section)
- [Making a table of contents](#making-a-table-of-contents)
- [Footnotes](#footnotes)
- [What is a package?](#what-is-a-package)
- [Table](#table)
- [Adding images](#adding-images)
- [Insert code into LaTeX](#insert-code-into-latex)
- [Multiple files in LaTeX](#Multiple-files-in-LaTeX)
- [Additional Tools](#additional-tools)

## What is LaTeX?

LaTeX, which is pronounced «Lah-tech» or «Lay-tech» (to rhyme with «blech»), is a document preparation system for high-quality typesetting. It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

## Why use LaTeX?

- LaTeX is free, multiplatform.
- LaTeX is just a text document (which can be opened by any text editor), readily converted to PDF.
- LaTeX separates content and style. Style once, then focus on content.
- The workflow is faster compared to MS Word.
- LaTeX is widely used for scientific topics.
- LaTeX is simply the best option when it comes to typesetting math expressions.

> LaTeX doesn't come without drawbacks, but is still worth learning.

## Set up for LaTeX

You will need the following things:

1. _LaTeX Distribution._
   I am using [MiKTeX](https://miktex.org/about) for Windows.
2. _LaTeX Editor._
   I am using [TeXMaker](http://www.xm1math.net/texmaker/) for easy editing, although any text editor can create or change a LaTeX file.
3. _PDF viewer._ (optional)
   Any PDF viewer out there is fine. This is for viewing your result.

In addition, you need to choose a [compiler](#additional-tools). The default compiler of most
editors is pdfLaTeX, but if you need support for Unicode or TTF/OTF fonts from
your system, use LuaLaTeX.

Or you can choose a simple online solution like [ShareLaTeX](https://www.sharelatex.com/).
Please look at [Additional Tools](#additional-tools) for a wider variety of choices.

## First LaTeX file

Let's do the traditional **Hello World** in **LaTeX**.
If you have installed **TexMaker**, first create a new file with ending `.tex`. Then type in the following code below to render "Hello World!" and run "quick build". For other LaTeX editors, it should also be easy to follow the same procedure.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

It should look like this in TexMaker:
![](http://i.imgur.com/ZuD5N6U.png)

## A deeper look

:eyes: A deeper look into your first LaTeX file easily shows that:

- The first line tells the Interpreter that you are working on an **article** with the size of the a4. Other types of document you might be working with in the future are **report**, **book**... and so on.
- A document is wrapped by the **\begin{document}** and **\end{document}**. Think of this as the heart of the document, as the `main()` in _java_ or _C++_... without which the document can't be rendered.
- The part between begin and end ( which, in this case, is `Hello World` ) is simply your own content.
- A **percent sign** (%) denotes your comment, which LaTeX will ignore.

#### :zap: Attention :zap:

- Looking back at **\begin{document}**, **\end{document}**, **\documentclass[a4paper]{article}**. You may notice the pattern now. These are called **Typesetting Commands** ( which are usually preceded by “\” ) and **arguments** ( placed inside curly braces “{}” ). LaTeX are basically normal texts, but powered by these commands.
- While you are following this guide, everything will work smoothly. However, in the future, should there be any problems, **don't panic**. The error reports are human-friendly and readable. If you can't resolve them, a search tool like Google may be your best friend.
- Some characters are **predefined with special meanings in LaTeX. You may want to use backslashes (\\) in front of these characters for proper output.**

![](http://i.imgur.com/9d0bXHH.png)

## Multilingual usage

**Some languages won't work right out of the box. To use TeX with other languages, you have some options.**

#### :white_check_mark: First method :white_check_mark:

The first method is including ["packages"](#what-is-a-package) (You will learn about it later) because pdfLaTeX, the default compiler, is limited to 256 characters and various encoding issues. For example:

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Here we use the packages `usepackage[T5]{fontenc}` and `usepackage[utf8]{inputenc}`. This is really simple to understand as the package will import font encoders to display your content correctly. If you are using TexMaker this is what the above code display:

![](http://i.imgur.com/UQEewYi.png)

vs without the packages :package::

![](http://i.imgur.com/xvzrQX2.png)

:umbrella: A tricky situation is dealing with Chinese-Japanese-Korean. Here, `usepackage{CJKutf8}` with `\begin{CJK}{UTF8}` and `\end{CJK}` comes in very handy. Here's Japanese :jp::

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

As easy as eating :sushi: and :bento::

![](http://i.imgur.com/vAN1WUi.png)

#### :white_check_mark: Second method :white_check_mark:

Another method is achievable if you switch your TeX compiler to [LuaLaTeX](#additional-tools) (or [XeLaTeX](#additional-tools)). Using `fontspec` and `polyglossia`, Unicode will work out of the box:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

The default font (Latin Modern) does not support all characters. You can, however, use almost any font installed on your system by uncommenting the `\setmainfont` line. (TTF and OTF fonts are fully supported).

## Lists

:straight_ruler: It is very important to organize your document well. Thus, let's start by putting your items into a list.  
Two common types of lists are **unordered** and **ordered** list. Each of them can be handled with ease in LaTeX document:

- Unordered List  
  Unordered list only needs **"itemize"**. (pun intended)

```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```

- Ordered List  
  Ordered list, however, need us to **"enumerate"** them. (pun intended)

```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

Here's how two types of list display in the output:

![](http://i.imgur.com/jzN4RWm.png)

## Paragraph and section

:blue_book: We begin a section with `\section` and a paragraph with `\paragraph`.
:orange_book: You can also add subsection with `\subsection` and subparagraph with `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Making a table of contents

:metal: It's useful to open sections and subsections with a `\tableofcontents`

Example:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tips**: you can use `\newpage` if you want to make a new page.

## Footnotes

It's as easy as pie to use footnote+label+ref to make all kinds of footnotes you want. For example:

```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```

:point_down: :point_down: Can you see it ? :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tips**: you can use `\newline` to make a new line.

## What is a package?

LaTeX offers a lot of functions by default, but in some situations it can come in handy to use so called packages. To import a package in LaTeX, you simply add the `\usepackage` :package:

Here is an example of using two packages for displaying math:

![](http://i.imgur.com/050nrfh.png)

Even more epic is how circuits are displayed:

![](http://i.imgur.com/If4lbLA.png)

:construction: You should Google search more if you want a package that meets your requirements. For example, amsmath is widely used for math and has a lot of extension typeset for math, circuitikz is for circuits designing, etc.. Covering them all would be impossible for this general guide.

## Table

A practical example :thought_balloon::

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

:star2: This is what it renders :star2::

![](http://i.imgur.com/XbZJJ2E.png)

Now let's take a closer look :eyes::

- For tables, first we need a table environment, which is why we have `\begin{table}` and `\end{table}`.
- You will learn about h! later in the image section. It goes with `\centering` to keep the table at the center of the page.
- Caption is for describing. Label is for tagging. You will see these more in image section.
- Tabular is the most important part. A table environment always needs a tabular environment inside.
  - the part `{l|c||r}` is where we format the content inside the table. Here we can see:
    - l or c or r means that the content inside each cell will be left-aligned or center-aligned or right-aligned, respectively.
    - the vertical slash | or || is actually the format of the vertical lines/borders inside the table's columns.
  - 1 & 2 & 3 => 1 2 3 are the contents of each cells. the ampersand & is used to separate the content of each cell in a row.
  - a `\hline` actually adds a horizontal line to separate each row.

:bangbang: **Tips**: You can use a package :package: called booktabs `\usepackage{booktabs}` for a visually better table.

## Adding images

To add an image to the LaTeX file, you need to use figure environment and the graphicx package. Use `\usepackage{graphicx}` and

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Tips**: Put [width=\linewidth] to scale the image to the width of the document. If you want to float the image, then you need to attribute the begin with a certain value. Also, the fig is for later reference so name it with care.

```tex
\begin{figure}[h!]
```

:passport_control: Legit values are:

- h (here) — same location
- t (top) — top of page
- b (bottom) — bottom of page
- p (page) — on an extra page
- ! (override) — will force the specified location

Here's how the image is rendered:

![](http://i.imgur.com/ysY9MOb.png)

## Insert code into LaTeX

#### :white_check_mark: First method :white_check_mark:

One aspect of text compiling that is of the utmost importance to programmers and developers is how to professionally insert codes into the document.

For LaTeX, the process is simple and very professional. We just wrap the code with some predefined content, then we are good to go.

Example:

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

:speech_balloon: **LaTeX supports syntax for these languages** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

As you can see, with the **{verbatim}** wrapper you can easily insert code without worrying about how the syntax is formatted. Here is how it looks out of the box, clean and professional:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Second Method :white_check_mark: :white_check_mark:

This method gives you more options, including insert code **inline**, make **custom styles** code, choose a **specific language** for code, **import code** **from** another **file** within the same directory.... With this method, you dont use **{verbatim}**, but include a package :package: named **listings**.

Consider the following example:

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

From this, you can see:

1. To insert a code block, start with `\begin{lstlisting}` and end with `\end{lstlisting}`
2. To import code from another file within the same directory, you can use `lstinputlisiting{name_of_file}`
3. To specify a language for the code, use `[language=C++]`
4. To insert inline code use `\lstinline`
5. To apply custom styles, use the `\usepackage{color}` and define your own style then define the listing with your own theme (Please look at code below). You can modify many things with your own style, but you need to read the doc for the correct property name.
6. Interested ?? More [here](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Here is how the code above compiles in TexMaker:

![](http://i.imgur.com/XwwDJNo.png)

## Multiple files in LaTeX

When we use LaTeX, we may face a problem that a document is too long to be handle. Therefore, we should divide the file so that its contents can be easily handled.

Let's look at the example:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

It's just a normal LaTeX file. Now, let's divide the document into two parts using the `\input` keyword:

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

Now the main file looks different, but better documented. Here is the result in TeXShop on Mac:
![image](https://user-images.githubusercontent.com/15828926/100050360-d079cc00-2e4b-11eb-8cb5-7e4fc2fd97f1.png)

:bangbang: **Tips**: For readability, clarity and maintenance purpose, it is highly suggested that you divide your Main file systematically, hierarchically and scientifically. Don't divide without reasons or you may get a mess later.

## Additional Tools

#### Distributions

- [MiKTeX](https://miktex.org/about) for Windows.
- [TeX Live](https://www.tug.org/texlive/) for Linux and Unix-based.
- [MacTeX](https://tug.org/mactex/) for macOS.
- [ShareLaTeX](https://www.sharelatex.com/) — an online editor.
- [Overleaf](https://www.overleaf.com/) — an collaborative online editor.
- [StackEdit](https://stackedit.io/) — In-browser markdown editor.

#### LaTeX Editors

- [TeXMaker](http://www.xm1math.net/texmaker/) Cross platform LaTeX editor.
- [TeXStudio](http://www.texstudio.org/) An enhanced fork of TeXMaker with more features.
- TeXShop and TeXworks (minimal editors)

#### LaTeX Compilers

- Most editors will have an option for you to change the default compiler. Here's an example:

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY!!

:tada: Thank you for finishing the guide. That's basically all you need to know about LaTeX. :hammer:  
If you are greatly interested, more on LaTeX can be found [here](http://www.latex-project.org/help/documentation/) or all over the web, depending on your need.

## License

[![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION: You just DO WHAT THE FUCK YOU WANT TO.

<div id='donation'/>

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

A beer in your country can buy a meal in mine.
