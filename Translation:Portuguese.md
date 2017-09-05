
# Comece com o LaTeX em minutos

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Aviso:** *Todo conteúdo escrito abaixo é de minha própria experiência na faculdade e da leitura de diversos materiais. Eu não sou nem professional nem especialista, mas um estudante com uma grande paixão pela linguagem. Qualquer um pode abrir uma discussão na seção issue, ou um pull request no caso de algo que deve ser modificado ou adicionado. Se você considera meu trabalho valioso, uma [doação](#doação) é muito apreciada.*

*Versão em chinês disponível [Aqui](https://github.com/VoLuong/Begin-Latex-in-minutes/blob/master/Translation:Chinese.md)*  
*Versão em espanhol disponível  [Aqui](https://github.com/VoLuong/Begin-Latex-in-minutes/blob/master/Translation:Spanish.md)*

### Tabela de Conteúdos
* [O que é LaTeX?](#o-que-é-latex)
* [Por quê usar LaTeX?](#por-quê-usar-latex)
* [Configurar LaTeX](#configurar-latex)
* [Primeiro Arquivo LaTeX](#primeiro-arquivo-latex)
* [Um olhar mais profundo](#um-olhar-mais-profundo)
* [Uso multilíngue](#uso-multilíngue)
* [Listas](#listas)
* [Paragrafo e seção](#paragráfo-e-seção)
* [Fazendo uma tabela de conteúdos](#fazendo-uma-tabela-de-conteúdos)
* [Notas de rodapé](#notas-de-rodapé)
* [O que é um pacote](#o-que-é-um-pacote)
* [Tabela](#tabela)
* [Adicionando imagens](#adicionando-imagens)
* [Insira código no LaTeX](#insira-código-no-latex)
* [Vários arquivos no LaTeX](#vários-arquivos-no-latex)
* [Ferramentas adicionais](#ferramentas-adicionais)

## O que é LaTex?

LaTeX, que é pronunciado «Lah-tech» ou «Lay-tech» (para rimar com «blech»), é um sistema de preparação de documentos para a tipografia de alta qualidade. É usado geralmente para documentos técnicos ou cientifícos, médios ou grandes, mas também pode ser usado para quase todas as formas de publicação.



## Por quê usar LaTeX?

* LaTeX é gratuito, multiplataforma.
* LaTeX é apenas um documento de texto (que pode ser aberto por qualquer editor de texto), pronto para ser convertido em pdf.
* LaTeX separa o conteúdo do estilo. Uma vez que o estilo é definido, podemos nos concentrar no conteúdo.
* O fluxo de trabalho é mais rápido se comparado ao MS Word.
* LaTeX é amplamente usado em temas científicos.
* LaTeX é simplesmente a melhor opção quando se trata de escrever expressões matemáticas.

> LaTeX não vem sem incovenientes, mas ainda vale a pena aprendê-lo.

## Configurar LaTeX

Precisarás do seguinte:


1. *Uma distribuição LaTeX.*
Eu estou usando [MiKTeX](https://miktex.org/about) para Windows.
2. *Um editor LaTeX.*
Eu estou usando [TeXMaker](http://www.xm1math.net/texmaker/) para facilitar a edição, embora qualquer editor de texto possa criar ou modificar um arquivo LaTeX.
3. *Um visualizador de PDF.* (opcional)
Qualquer visualizador de pdf servirá. Isto será usado para que você veja o resultado de seu trabalho.

Ademais, você precisa escolher um [compiler](#additional-tools). O compilador padrão para maioria dos editores é o pdfLateX, mas se você precisar de suporte para as fontes TTF/OTF do seu sistema, use LuaLateX. 

Também é possível escolher uma solução online como [ShareLaTeX](https://www.sharelatex.com/).
Por favor olhe nas [Additional Tools](#additional-tools) para uma ampla variedade de opções.

## Primeiro Arquivo LaTeX 

Vamos fazer o famoso **Hello World** no **LaTeX**.
Se você já tem instalado o **TexMaker**, primeiro crie um novo arquivo com a extensão `.tex`. Então digite o seguinte código abaixo para renderizar o "Hello World!" e pressione o botão de "construção rápida". Para outros editores LaTeX, deve ser fácil seguir o mesmo procedimento.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % Este é o seu conteúdo

\end{document}
```

It should look like this in TexMaker:
![](http://i.imgur.com/ZuD5N6U.png)

## Um olhar mais profundo

:eyes: Um olhar mais profunfo sobre seu primeiro arquivo LaTeX mostra que :
* A primeira linha diz ao interpretador que você está trabalhando em um **artigo(article)** de tamanho A4. Outros tipos de documentos que você poderá está trabalhando no futuro são **relatório(report)**, **livro(book)**... dentre outros.
* Um documento que é delimitado pelo **\begin{document}** e **\end{document}** . Pense nisto como sendo o núcleo do documento, como o `main()` em *java* ou *C++* ..., sem ele o documento não poderá ser renderizado. 
* A parte entre o **\begin{document}** e **\end{document}** ( que, neste caso, é `Hello World` ) é simplesmente seu próprio conteúdo.
* Um **simbólo de porcentagem** (%) indica comentários, que serão ignorados pelo LaTeX.

#### :zap: Atenção :zap: 

* Olhando novamente para o documento **\begin{document}** , **\end{document}** , **\documentclass[a4paper]{article}** . Você poderá notar esse padrão agora. Eles são chamados de  **Comandos de Configuração** ( que geralmente são precedidos por “\” ) e precisam de **argumentos** ( colocados dentro de “{}” ). LaTeX é um texto normal, que é embelezado por esses comandos.
* Enquanto você está seguindo este tutorial, tudo deverá sair bem. No entanto, no futuro, poderás ter alguns problemas, **não entre em pânico**. Os relatórios de erros são amigáveis e legíveis. Se você não conseguir resolvê-los uma ferramenta de pesquisa como o Google poderá ser sua melhor amiga.  
* Alguns caracteres estão **predefinidos com significados especiais no LaTeX. Você deverá usar duas barras invertidas (\\) na frente desses caracteres para obter a saída adequada.**  

![](http://i.imgur.com/9d0bXHH.png)   

## Uso multilíngue

** Algumas linguagens ou idiomas não funcionarão de imediato(como é o caso do português com seus acentos). Para usar o LaTeX com outras linguagens, temos algumas opções:** 
  

#### :white_check_mark: Primeiro método :white_check_mark:

O primeiro método está incluindo ["pacotes"](#o-que-é-um-pacote) (Você irá aprender sobre isso depois) porque o compilador padrão do pdfLaTeX, está limitado à 256 caracteres e vários problemas de codificação. Por exemplo:  

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Aqui nós usamos os pacotes `usepackage[T5]{fontenc}` e `usepackage[utf8]{inputenc}` . Isso é realmente simples de entender, o pacote irá importar a codificação das fontes para exibir seu conteúdo corretamente. Se você está usando TexMaker o codigo anterior será exibido da seguinte maneira:

![](http://i.imgur.com/UQEewYi.png)

vs sem os pacotes :package::  

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: Uma situação complicada é lidar com caracter Chinês-Japonês-Korean. Aqui, `usepackage{CJKutf8}` com`\begin{CJK}{UTF8}` e `\end{CJK}` são bastante úteis. Aqui está um exemplo da forma de escrever em Japonês :jp: : 
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

Tão fácil quanto comer :sushi: e :bento: : 

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: Segundo método :white_check_mark:
Outro método viável é se você mudar seu compilador TeX para [LuaLaTeX](#ferramentas-adicionais) (ou [XeLaTeX](#ferramentas-adicionais)). Usando `fontspec` e `polyglossia`, Unicode irá funcionar corretamente:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

A fonte padrão (Latin Modern) não suporta todos os caracteres. Você pode, no entanto, usar qualquer outra fonte instalada no seu systema descomentando a linha `\setmainfont`. ( As fontes TTF e OTF são totalmente suportadas).


## Listas

:straight_ruler: It is very important to organize your document well. Thus, let's start by putting your items into a list.  
Two common types of lists are **unordered** and **ordered** list. Each of them can be handled with ease in LaTeX document :  
* Unordered List  
Unordered list only needs **"itemize"**. (pun intended)
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```  
* Ordered List  
Ordered list, however, need us to **"enumerate"** them. (pun intended)  
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

Here's how two types of list display in the output: 

![](http://i.imgur.com/jzN4RWm.png)

## Paragráfo e seção

:blue_book: We begin a section with `\section` and a paragraph with `\paragraph` .
:orange_book: You can also add subsection with `\subsection` and subparagraph with `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Fazendo uma tabela de conteúdos

:metal: It's useful to open sections and subsections with a `\tableofcontents`

Example:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tips** : you can use `\newpage` if you want to make a new page.

## Notas de rodapé

It's as easy as pie to use footnote+label+ref to make all kinds of footnotes you want. For example:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: Can you see it ?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tips** : you can use `\newline` to make a new line.

## O que é um pacote?

LaTeX offers a lot of functions by default, but in some situations it can come in handy to use so called packages. To import a package in LaTeX, you simply add the `\usepackage` :package:

Here is an example of using two packages for displaying math:

![](http://i.imgur.com/050nrfh.png)  

Even more epic is how circuits are displayed: 

![](http://i.imgur.com/If4lbLA.png)

:construction: You should google search more if you want a package that meets your requirements. For example, amsmath is widely used for math and has a lot of extension typeset for math, circuitikz is for circuits designing, etc.. Covering them all would be impossible for this general guide.

## Tabela

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

![](http://i.imgur.com/XbZJJ2E.png)

Now let's take a closer look :eyes: :

* For tables, first we need a table environment, which is why we have `\begin{table}` and `\end{table}` .
* You will learn about h! later in the image section. It goes with `\centering` to keep the table at the center of the page.
* Caption is for describing. Label is for tagging. You will see these more in image section.
* Tabular is the most important part. A table environment always needs a tabular environment inside.
  - the part `{l|c||r}` is where we format the content inside the table. Here we can see :
    * l or c or r means that the content inside each cell will be left-aligned or center-aligned or right-aligned, respectively.
    * the vertical slash | or || is actually the format of the vertical lines/borders inside the table's columns.
  - 1 & 2 & 3 => 1 2 3 are the contents of each cells. the ampersand & is used to separate the content of each cell in a row.
  - a `\hline` actually adds a horizontal line to separate each row.

:bangbang: **Tips** You can use a package :package: called booktabs `\usepackage{booktabs}` for a visually better table.

## Adicionando imagens

To add an image to the LaTeX file , you need to use figure environment and the graphicx package. Use `\usepackage{graphicx}` and

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

## Insira código no LaTeX

#### :white_check_mark: First method :white_check_mark:

One aspect of text compiling that is of the utmost importance to programmers and developers is how to professionally insert codes into the document.

For LaTeX, the process is simple and very professional. We just wrap the code with some predefined content, then we are good to go.

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

:speech_balloon: **LaTeX supports syntax for these languages** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

As you can see, with the **{verbatim}** wrapper you can easily insert code without worrying about how the syntax is formatted. Here is how it looks out of the box, clean and professional :

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Second Method :white_check_mark: :white_check_mark:

This method gives you more options, including insert code **inline**, make **custom styles** code, choose a **specific language** for code, **import code** **from** another **file** within the same directory.... With this method, you dont use **{verbatim}** , but include a package :package: named **listings**.

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
a
1. To insert a code block , start with `\begin{lstlisting}` and end with `\end{lstlisting}`
2. To import code from another file within the same directory, you can use `lstinputlisiting{name_of_file}`
3. To specify a language for the code, use `[language=C++]`
4. To insert inline code use `\lstinline`
5. To apply custom styles, use the `\usepackage{color}` and define your own style then define the listing with your own theme (Please look at code below). You can modify many things with your own style, but you need to read the doc for the correct property name.
6. Interested ?? More [here](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Here is how the code above compiles in TexMaker :

![](http://i.imgur.com/XwwDJNo.png)

## Vários arquivos no LaTeX

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

Now the main file looks different, but better documented. Here is the result in TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Tips** : For readability, clarity and maintenance purpose, it is highly suggested that you divide your Main file systematically, hierarchically and scientifically. Don't divide without reasons or you may get a mess later.  

## Ferramentas Adicionais

#### Distributions

* [MiKTeX](https://miktex.org/about) for Windows.
* [TeX Live](https://www.tug.org/texlive/) for Linux and Unix-based.
* [MacTeX](https://tug.org/mactex/) for macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — an online editor.
* [Overleaf](https://www.overleaf.com/) — an collaborative online editor.
* [StackEdit](https://stackedit.io/) - In-browser markdown editor.

#### LaTeX Editors

* [TeXMaker](http://www.xm1math.net/texmaker/) Cross platform LaTeX editor.
* [TeXStudio](http://www.texstudio.org/) An enhanced fork of TeXMaker with more features.
* TeXShop and TeXworks (minimal editors)

#### LaTeX Compilers

* Most editors will have an option for you to change the default compiler. Here's an example : 

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY !!

:tada: Thank you for finishing the guide. That's basically all you need to know about LaTeX. :hammer:  
If you are greatly interested, more on LaTeX can be found [here](http://www.latex-project.org/help/documentation/) or all over the web, depending on your need.

## Licença

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION : You just DO WHAT THE FUCK YOU WANT TO.  



<div id='doação'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

A beer in your country can buy a meal in mine.
