<<<<<<< HEAD
# Begin LATEX in minutes

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)  

*Inspired by my professor Nghiem Quoc Minh*

### Table of Contents
* [What is Latex](#what-is-latex)
* [Why use Latex](#why-use-latex)
* [Set up for Latex](#set-up-for-latex)
* [First Latex file](#first-latex-file)
* [A deeper look](#a-deeper-look)
* [Paragraph and section](#paragraph-and-section)
* [Making a table of contents](#making-a-table-of-content)
* [Footnotes](#footnotes)
* [What is package](#what-is-package)
* [Table](#table)
* [Adding images](#adding-images)
* [Insert code into Latex](#insert-code-into-latex)

## What is Latex?

LaTeX, which is pronounced «Lah-tech» or «Lay-tech» (to rhyme with «blech» or «Bertolt Brecht»), is a document preparation system for high-quality typesetting. It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

## Why use Latex?

* Latex is free, multiplatform.
* Latex is just a text document (which can be opened by any text editor), and readily converted to PDF.
* Latex separates content and style. Style once, then focus on content.
* The workflow is faster compared to MS Word.
* Latex is widely used for scientific topics.

Latex doesnt come without drawbacks, but is still worth learning.

## Set up for Latex

You will need two things:  

1. *Latex Interpreter/Compiler.*   
I suggest [Miktex](https://miktex.org/about) for Windows. [TeXLive](https://www.tug.org/texlive/) for Linux and Unix-based. [MacTeX](https://tug.org/mactex/) for Mac
2. *Latex Editor.*  
I highly suggest [TexMaker](http://www.xm1math.net/texmaker/) for easy editing, although any text editor can create or change a latex file.
3. *PDF viewer.* (optional)   
Any PDF viewer out there is fine. This is for viewing your result.  

Or you can choose a simple online solution : [ShareLatex](https://www.sharelatex.com/).  

## Your first Latex file

Let's do the traditional **Hello World** in **Latex**.
If you have installed **TexMaker**, first create a new file with ending ```.tex```. Then type in the following code below to render "Hello World!" and run "quick build"

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World

\end{document}
```

It should look like this in TexMaker:   
![](http://i.imgur.com/XJxoXyI.jpg)  

## A deeper look

:eyes: A deeper look into your first latex file easily shows that:
* The first line tells the Interpreter that you are working on an **article** with the size of the a4. Other types of document you might be working with in the future are **report**, **book**, and so on.
* A document is wrapped by the **\begin{document}** and **\end{document}** . Think of this as the heart of the document, as the ```main()``` in *java* or *C++* ... without which the document can't be rendered.
* The part between begin and end ( which, in this case, is ```Hello World``` ) is simply your own content.

### :warning: Important :warning:   
**Some languages won't work right out of the box. You will need to include some packages for the font to render. Also, you will learn about "packages" later.** For example:  

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hellow World in Vietnamese.

\end{document}
```

Here we use two packages ```usepackage[T5]{fontenc}``` and ```usepackage[utf8]{inputenc}``` . This is really simple to understand as the package will import font encoders to display your content correctly. If you are using TexMaker this is what the above code displays:

![](http://i.imgur.com/OUSPekM.png)

vs without the packages :package::  

![](http://i.imgur.com/Upd47xH.png)  

## Paragraph and section

:blue_book: We begin a section with ```\section``` and a paragraph with ```\paragraph``` .   
:orange_book: You can also add subsection with ```\subsection``` and subparagraph with ```\subparagraph```  

![](http://i.imgur.com/qKbZYnG.png)

## Making a table of contents

:metal: It's useful to open sections and subsections with a ```\tableofcontents```

Example:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tips** : you can use ```\newpage``` if you want to make a new page.

## Footnotes

It's as easy as pie to use footnote+label+ref to make all kinds of footnotes you want. For example:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: Can you see it ?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tips** : you can use ```\newline``` to make a new line.  

## What is a package?

LaTeX offers a lot of functions by default, but in some situations it can come in handy to use so called packages. To import a package in LaTeX, you simply add the ```\usepackage``` :package:  

Here is an example of using two packages for displaying math:

![](http://i.imgur.com/jF3oNY0.png)  

:construction: You should google search more if you want a package that meets your requirements. For example, amsmath is widely used for math and has a lot of extension typeset for math. Covering them all would be impossible for this general guide.

## Table

A practical example :thought_balloon: :   

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

:star2: This is what it renders :star2: :

![](http://i.imgur.com/3Wxn9oB.png)  

Now let's take a closer look :eyes: :

* For tables, first we need a table environment, which is why we have ```\begin{table}``` and ```\end{table}``` .
* You will learn about h! later in the image section. It goes with ```\centering``` to keep the table at the center of the page.
* Caption is for describing. Label is for tagging. You will see these more in image section.
* Tabular is the most important part. A table environment always needs a tabular environment inside.
  - the part ```{l|c||r}``` is where we format the content inside the table. Here we can see:
    * l or c or r means that the content inside each cell will be left-aligned or center-aligned or right-aligned, respectively.
    * the vertical slash | or || is actually the format of the vertical lines/borders inside the table's columns.
  - 1 & 2 & 3 => 1 2 3 are the contents of each cells. the ampersand & is used to separate the content of each cell in a row.
  - a ```\hline``` actually adds a horizontal line to separate each row.

:bangbang: **Tips** You can use a package :package: called booktabs ```\usepackage{booktabs}``` for a visually better table.

## Adding images

To add an image to the latex file , you need to use figure environment and the graphicx package. Use ```\usepackage{graphicx}``` and

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Tips**: Put [width=\linewidth] to scale the image to the width of the document.  If you want to float the image, then you need to attribute the begin with a certain value. Also, the fig is for later reference so name it with care.  

```tex
\begin{figure}[h!]
```

:passport_control: Legit values are :   

* h (here) - same location
* t (top) - top of page
* b (bottom) - bottom of page
* p (page) - on an extra page
* ! (override) - will force the specified location

Here's how the image is rendered :  

![](http://i.imgur.com/ysY9MOb.png)

## Insert code into Latex  

#### :white_check_mark: First method :white_check_mark:

One aspect of text compiling that is of the utmost importance to programmers and developers is how to professionally insert codes into the document.

For Latex, the process is simple and very professional. We just wrap the code with some predefined content, then we are good to go.  

Example :  

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

:speech_balloon: **Latex supports syntax for these languages** :speech_balloon:    

![](http://i.imgur.com/FJfj8Er.png)    

As you can see, with the **{verbatim}** wrapper you can easily insert code without worrying about how the syntax is formatted. Here is how it looks out of the box, clean and professional :

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Second Method :white_check_mark: :white_check_mark:

This method gives you more options, including insert code **inline**, make **custom styled** code, choose a **specific language** for code, **import code** **from** another **file** within the same directory.... With this method, you dont use **{verbatim}** , but include a package :package: named **listings**.    

Consider the following example :
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

1. To insert a code block, start with ```\begin{lstlisting}``` and end with ```\end{lstlisting}```  
2. To import code from another file within the same directory, you can use ```lstinputlisiting{name_of_file}```  
3. To specify a language for the code, use ```[language=C++]```  
4. To insert inline code use ```\lstinline```  
5. To apply custom styles, use the ```\usepackage{color}``` and define your own style then define the listing with your own theme (Please look at code below). You can modify many things with your own style, but you need to read the docs for the correct property name.  
6. Interested? More [here](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).  

Here is how the code above compiles in TexMaker :  

![](http://i.imgur.com/XwwDJNo.png)

## HOORAY !!

:tada: Thank you for finishing the guide. That's basically all you need to know about LaTex. :hammer:  

## License

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo  
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION : You just DO WHAT THE FUCK YOU WANT TO.
