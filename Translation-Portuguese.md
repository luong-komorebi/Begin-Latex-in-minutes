[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
Português ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# Comece com o LaTeX em minutos

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

(Portuguese translator's acknowledgement: I tried to translate this guide as the original meaning of the author as much as i could. If you think the translation is inappropriate, please feel free to modify it or add missing stuff you think would make this guide better. If you like this guide, please share to more people.)

**Aviso:** *Todo conteúdo escrito abaixo é de minha própria experiência na faculdade e da leitura de diversos materiais. Eu não sou nem professional nem especialista, mas um estudante com uma grande paixão pela linguagem. Qualquer um pode abrir uma discussão na seção issue, ou um pull request no caso de algo que deve ser modificado ou adicionado. Se você considera meu trabalho valioso, uma [doação](#doação) é muito apreciada.*

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

Ademais, você precisa escolher um [compilador](#ferramentas-adicionais). O compilador padrão para maioria dos editores é o pdfLateX, mas se você precisar de suporte para as fontes TTF/OTF do seu sistema, use LuaLateX. 

Também é possível escolher uma solução online como [ShareLaTeX](https://www.sharelatex.com/).
Por favor olhe nas [Ferramentas adicionais](#ferramentas-adicionais) para uma ampla variedade de opções.

## Primeiro Arquivo LaTeX 

Vamos fazer o famoso **Hello World** no **LaTeX**.
Se você já tem instalado o **TexMaker**, primeiro crie um novo arquivo com a extensão `.tex`. Então digite o seguinte código abaixo para renderizar o "Hello World!" e pressione o botão de "construção rápida". Para outros editores LaTeX, deve ser fácil seguir o mesmo procedimento.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % Este é o seu conteúdo

\end{document}
```

Você deve ver isso no TexMaker:
![](http://i.imgur.com/ZuD5N6U.png)

## Um olhar mais profundo

:eyes: Um olhar mais profundo sobre seu primeiro arquivo LaTeX mostra que :
* A primeira linha diz ao interpretador que você está trabalhando em um **artigo(article)** de tamanho A4. Outros tipos de documentos que você poderá está trabalhando no futuro são **relatório(report)**, **livro(book)**... dentre outros.
* Um documento que é delimitado pelo **\begin{document}** e **\end{document}** . Pense nisto como sendo o núcleo do documento, como o `main()` em *java* ou *C++* ..., sem ele o documento não poderá ser renderizado. 
* A parte entre o **\begin{document}** e **\end{document}** ( que, neste caso, é `Hello World` ) é simplesmente seu próprio conteúdo.
* Um **símbolo de porcentagem** (%) indica comentários, que serão ignorados pelo LaTeX.

#### :zap: Atenção :zap: 

* Olhando novamente para o documento **\begin{document}** , **\end{document}** , **\documentclass[a4paper]{article}** . Você poderá notar esse padrão agora. Eles são chamados de  **Comandos de Configuração** ( que geralmente são precedidos por “\” ) e precisam de **argumentos** ( colocados dentro de “{}” ). LaTeX é um texto normal, que é embelezado por esses comandos.
* Enquanto você está seguindo este tutorial, tudo deverá sair bem. No entanto, no futuro, poderás ter alguns problemas, **não entre em pânico**. Os relatórios de erros são amigáveis e legíveis. Se você não conseguir resolvê-los uma ferramenta de pesquisa como o Google poderá ser sua melhor amiga.  
* Alguns caracteres estão **predefinidos com significados especiais no LaTeX. Você deverá usar duas barras invertidas ("`\\`") na frente desses caracteres para obter a saída adequada.**  

![](http://i.imgur.com/9d0bXHH.png)   

## Uso multilíngue

**Algumas linguagens ou idiomas não funcionarão de imediato(como é o caso do português com seus acentos). Para usar o LaTeX com outras linguagens, temos algumas opções:** 
  

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

:umbrella: Uma situação complicada é lidar com caractere Chinês-Japonês-Koreano. Aqui, `usepackage{CJKutf8}` com`\begin{CJK}{UTF8}` e `\end{CJK}` são bastante úteis. Aqui está um exemplo da forma de escrever em Japonês :jp: : 
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
Outro método viável é se você mudar seu compilador TeX para [LuaLaTeX](#ferramentas-adicionais) (ou [XeLaTeX](#ferramentas-adicionais)). Usando `fontspec` e `polyglossia`, o Unicode irá funcionar corretamente:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

A fonte padrão (Latin Modern) não suporta todos os caracteres. Você pode, no entanto, usar qualquer outra fonte instalada no seu sistema descomentando a linha `\setmainfont`. ( As fontes TTF e OTF são totalmente suportadas).


## Listas

:straight_ruler: É muito importante organizar bem o seu documento. Então, vamos começar a colocar seus itens em uma lista.  
Dois tipos de listas são comuns **não ordenadas** e **ordernadas**. Cada uma pode ser fácilmente manipulada em um documento LaTeX :  
* Lista não ordenada  
Listas não ordenadas precisam apenas do  **"itemize"**.
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```  
* Lista Ordenada  
Listas ordenadas, no entanto, precisam de  **"enumerate"**.
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

Aqui estão, como os dois tipos de lista são exibidos na saída: 

![](http://i.imgur.com/jzN4RWm.png)

## Paragráfo e seção

:blue_book: Nós iniciamos uma seção com `\section` e um paragráfo com `\paragraph` .
:orange_book: Você também pode adicionar uma subseção com `\subsection` e um subparagráfo com `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Fazendo uma tabela de conteúdos

:metal: É útil para abrir seções e subseções com uma `\tableofcontents`

Exemplo:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Dica** : Você pode usar `\newpage` se você quiser criar uma nova página.

## Notas de rodapé

É extremamente fácil usar footnote+label+ref para fazer todos os tipos de notas de rodapé que você queira. Por exemplo:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: Podes vê-lo ?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Dica** : Você pode usar `\newline` para fazer uma nova linha.

## O que é um pacote?

LaTeX oferece uma gama de funções por padrão, mas em algumas situações pode ser útil utilizar os chamados pacotes. Para importar um pacote no LaTeX, você simplesmente adiciona `\usepackage` :package:

Aqui está um exemplo de como usar dois pacotes para exibir expressões matemáticas:

![](http://i.imgur.com/050nrfh.png)  

Mais épico é como os circuitos são exibidos: 

![](http://i.imgur.com/If4lbLA.png)

:construction: Você deve pesquisar mais no google se você quiser um pacote que atenda a sua exigência. Por exemplo, amsmath é amplamente usado para escrever expressões matemáticas, circuitikz é para o desenho de circuits, etc..Explicar todos seria impossível neste tutorial.

## Tabela

Um exemplo prático :thought_balloon: :

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

:star2: Isto é o que será renderizado :star2: :

![](http://i.imgur.com/XbZJJ2E.png)

Vejamos detalhadamente :eyes: :

* Para tabelas precisamos do ambiente `\begin{table}`,  `código para o conteúdo da tabela`  e `\end{table}` .
* Você irá aprender sobre h! depois na seção de imagem. Use `\centering` para manter a tabela no centro da página.
* Caption é para descrever. Label é para colocar etiquetas. Você verá melhor isso na seção de imagens.
* Tabular é a parte mais importante. Um ambiente de tabela sempre precisa de um `tabular` dentro.
  - A parte `{l|c||r}` é onde nós formatamos o conteúdo dentro da tabela. Aqui nós podemos ver :
    * l ou c ou r significa que o conteúdo dentro de cada célula irá ser alinhado à esquerda ou ao centro ou à direita, respectivamente.
    * A `|` or `||` representam o formato das linhas(margens) verticais entre colunas.
  - 1 & 2 & 3 => 1 2 3 são os conteúdos de cada célula. O & é usado para separar o conteúdo de cada célula em uma linha.
  - Um `\hline` atualmente adiciona uma linha horizontal para separar cada coluna.

:bangbang: **Dica** Você pode usar um pacote :package: chamado booktabs `\usepackage{booktabs}` para uma visualização melhor da tabela.

## Adicionando imagens

Para adicionar um arquivo de imagem ao LaTeX, você precisa usar um ambiente de figuras e o pacote graphicx. 

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Dica**: Coloque [width=\linewidth] para dimensionar a imagem para o tamanho do documento.  Se você quiser que a imagem seja flutuante, então você precisa atribuir ao ínicio um certo valor. Também, `fig` é para tornar disponível uma referência da imagem em um uso posterior.

```tex
\begin{figure}[h!]
```

:passport_control: Os valores aceitos são :

* h (here) - Mesma localização
* t (top) - Parte superior da página
* b (bottom) - Parte inferior  da página
* p (page) - Página extra
* ! (override) - Força à uma localização indicada

Aqui está a imagem que será renderizada :

![](http://i.imgur.com/ysY9MOb.png)

## Insira código no LaTeX

#### :white_check_mark: Primeiro método :white_check_mark:

Um aspecto da compilação de texto é que ela é muito importante para programadores e desenvolvedores, é como profissionalmente se insere código em um documento.
Para LaTeX, o processo é simples e muito profissional. Nós apenas envolvemos o código com algum conteúdo pré-definido.

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

:speech_balloon: **LaTeX suporta sintaxe para essas linguagens** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

Como você pode ver, com o  `{verbatim}` você pode fácilmente inserir código sem se preocupar em como a sintaxe irá ser formatada. Aqui está como será exibida, limpo e profissional :

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Segundo Método :white_check_mark: :white_check_mark:

Esse método dá a você mais opções, incluindo inserir código **inline**, fazer **estilos próprios** de código, escolher uma **linguagem específica** para o código, **importar código** **de** outro **arquivo** em um mesmo diretório.... Com este método, você não usa `{verbatim}` , mas inclue um pacote :package: chamado `listings`.

Considere o seguinte exemplo :
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
Aqui podemos observar:
1. Para inserir um bloco de código , inicia-se com `\begin{lstlisting}` e finaliza-se com `\end{lstlisting}`
2. Para importar o código de um arquivo em um mesmo diretório, você pode usar `lstinputlisiting{name_of_file}`
3. Para especificar uma linguagem, use `[language=C++]`
4. Para inserir código inline, use `\lstinline`
5. Para aplicar estilos própios, use o `\usepackage{color}` e defina seu próprio estilo então defina uma lista com seu próprio tema (Por favor veja o código abaixo). Você pode modificar várias coisas com seu próprio estilo, mas você precisa ler a documentação para saber que propriedade modificar.
6. Interessado ?? Mais [Aqui](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Aqui está como o código acima compila no TexMaker :

![](http://i.imgur.com/XwwDJNo.png)

## Vários arquivos no LaTeX

Quando nós usamos LaTeX, nós podemos ter problemas de gerenciamento quando um documento é muito grande. No entanto, nós podemos devemos dividir o arquivo de forma que o conteúdo se torne mais fácil de manipular.

Vejamos um exemplo:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

É apenas um arquivo LaTeX normal. Agora, vamos dividir o documento em duas partes usando o comando `\input` keyword:


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

Agora o arquivo principal é diferente, mas melhor documentado e mais legível. Aqui está o resultado no TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Dica** : Para legibilidade, clareza e manutenção, é muito recomendado que você divida seu arquivo principal sistematicamente, hierarquicamente e cientifcamente. Não divida sem razões ou você terá uma bagunça depois.  

## Ferramentas Adicionais

#### Distribuições

* [MiKTeX](https://miktex.org/about) para Windows.
* [TeX Live](https://www.tug.org/texlive/) para Linux e sistemas baseados em Unix.
* [MacTeX](https://tug.org/mactex/) para macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — um editor online.
* [Overleaf](https://www.overleaf.com/) — um editor online colaborativo.
* [StackEdit](https://stackedit.io/) - Editor de Markdown no navegador.

#### Editores LaTeX

* [TeXMaker](http://www.xm1math.net/texmaker/) Um editor LaTeX multiplataforma.
* [TeXStudio](http://www.texstudio.org/) Um fork melhorado do TeXMaker com mais recursos.
* TeXShop e TeXworks (editores mínimos)

#### Compiladores LaTeX

* A maioria dos editores que tem uma opção para você modificador o compilador padrão. Aqui está um exemplo : 

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY !!

:tada: Obrigado por completar este tutorial. Isso é basicamente tudo que você precisa saber sobre LaTeX. :hammer:  
Se você está muito interessado, mais informações do LaTeX podem ser encontradas [aqui](http://www.latex-project.org/help/documentation/) ou em toda web, dependendo do que você precisa.

## Licença

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)
  
**LICENÇA PÚBLICA PARA FAZER O QUE LHE AGRADA**  
Copyright (C) 2016 Luong Vo  
É permitida a cópia e distribuição de cópias literais ou modificadas deste documento de licença, e a modificação é permitida desde que o nome seja alterado. (Alterar é permitido enquanto o nome for alterado).  
TERMOS E CONDIÇÕES DE CÓPIA, DISTRIBUIÇÃO E MODIFICAÇÃO: Claro, FAÇA O QUE LHE AGRADA.



<div id='doação'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

Uma cerveja no seu país pode comprar uma refeição no meu.
