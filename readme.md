# Intro to LATEX

### Table of content
* [What is Latex](#what-is-latex)
* [Why use Latex](#why-use-latex)
* [Set up for Latex](#set-up-for-latex)
* [First Latex file](#first-latex-file)
* [A deeper look](#a-deeper-look)
* [Insert code into Latex](#insert-code-into-latex)

## What is Latex

LaTeX, which is pronounced «Lah-tech» or «Lay-tech» (to rhyme with «blech» or «Bertolt Brecht»), is a document preparation system for high-quality typesetting. It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

## Why use Latex

* Latex is free, mutiplatform.
* Latex is just a text document (which can be opened by any text editor), readily converted to PDF.
* Latex separate content and style. Style once, then focus on content.
* The workflow is faster compared to MS Word.
* Latex is widely used for scientific topics.

> It doesnt come without drawbacks, but is still worthy to learn.

## Set up for Latex

You will need two things :
1. *Latex Interpreter.*
I highly suggest [miktex](https://miktex.org/about).
2. *Latex Editor.*
I highly suggest [TexMaker](http://www.xm1math.net/texmaker/), although any text editor should be capable of compiling a latex file.
3. *PDF viewer.*
Any PDF viewer out there is fine.

## First Latex file

Let's do the traditional **Hello World** in **Latex**.
If you have installed **TexMaker**, first create a new file with ending ```.tex```. Then type in the following code below to render "Hello World!" and run "quick build"

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World

\end{document}
```

It should look like this in TexMaker   
![](http://i.imgur.com/XJxoXyI.jpg)  

## A deeper look

A deeper look into your first latex file easily show that :
* The first line tells the Interpreter that you are working on an **article** with the size of the a4. Other types of document you might be working with in the future is **report**, **book**...
* A document is wrapped by the **\begin{document}** and **\end{document}** . Think of this as the heart of the document, as the ```main()``` in *java* or *C++* ... without which the document can't be rendered.
* The part between begin and end ( which, in this case, is ```Hello World``` ) is simply your own content.

:warning: **Important** :warning:   
**Some language won't work right out of the box. You will need to include some package for the font to the render.** For example :  

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hellow World in Vietnamese.

\end{document}
```

Here we use two package ```usepackage[T5]{fontenc}``` and ```usepackage[utf8]{inputenc}``` . This is really simple to understand as the package will import font encoder to display your content correctly. If you are using TexMaker this is what the above code display :

![](http://i.imgur.com/OUSPekM.png)

vs without the packages :  

![](http://i.imgur.com/Upd47xH.png)  

## Insert code into Latex  

#### First method :

One aspect of text compiling, which is of top important to programmers and developers, is how to professionally insert the codes into the document.

For Latex, the process is simple and very professional. We just wrap the code with the some predefined content, then we are good to go.  

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

Latex supports syntax for these languages :  
![](http://i.imgur.com/FJfj8Er.png)  

As you can see, with the **{verbatim}** wrapper you can easily insert code without worrying about how the syntax is formatted. Here is how it looks out of the box, clean and professional :

![](http://i.imgur.com/tpercup.png)

#### Second Method :

This method gives you more options, including insert code **inline**, make custom styled code, choose a specific language for code, import code from another file within the same directory.... With this method, you dont use **{verbatim}** , but include a package named **listings**.    

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
1. To insert a code block , start with ```\begin{lstlisting}``` and end with ```\end{lstlisting}```
2. To import code from another file within the same directory, you can use ```lstinputlisiting{name_of_file}```
3. To specify a language for the code, use ```[language=C++]```
4. To insert inline code use ```\lstinline```
5. To apply custom style, use the ```\usepackage{color}``` and define your own style then define the listing with your own theme (Please look at code below). You can modify many things with your own style, but you need to read the doc for the correct property name.
6. Interested ?? More [here](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Here is how the code above compile in TexMaker :  

![](http://i.imgur.com/XwwDJNo.png)
