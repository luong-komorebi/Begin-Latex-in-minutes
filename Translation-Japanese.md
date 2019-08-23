[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
日本語 ·
[Polski](./Translation-Polish.md)

---

# すぐに始める LaTeX 入門

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

(Japanese translator's acknowledgement: I tried to translate this guide as the original meaning of the author as much as I could. If you think the translation is inappropriate, please feel free to modify it or add missing stuff you think would make this guide better. If you like this guide, please share to more people.)

**初めに:** *この文書に書いていることは、私が大学での経験や目を通したいくつかの資料に基づくものです。私は、プロフェッショナルな仕事をしているわけでも、専門家でもなく、大いなる情熱を持つ学生です。問題セクションでは、誰でも議論に参加することを歓迎しますし、修正や加えるべきことがあれば、プルリクエストをすることができます。 もし、私のプロジェクトに価値があると思えば、ぜひ[寄付](#donation)をお願いします。*

### 内容一覧
* [LaTeXって何?](#LaTeXって何?)
* [どうしてLaTeXを使うの?](#どうしてLaTeXを使うの?)
* [LaTeXの設定](#LaTeXの設定)
* [はじめてのLaTeXファイル](#はじめてのLaTeXファイル)
* [さらに詳しく](#さらに詳しく)
* [多言語での使用方法](#多言語での使用方法)
* [箇条書き](#箇条書き)
* [段落と節](#段落と節)
* [内容リストの作成方法](#内容リストの作成方法)
* [脚注](#脚注)
* [パッケージとは?](#パッケージとは?)
* [表組み](#表組み)
* [画像の表示](#画像の表示)
* [LaTeXへのコード挿入方法](#LaTeXへのコード挿入方法)
* [LaTeXでの複数ファイル分割方法](#LaTeXでの複数ファイル分割方法)
* [追加ツール](#追加ツール)

## LaTeXって何?

LaTeXは「ラテフ」もしくは「レイテフ」と発音され、高品質な文書編纂システムです。中規模から大規模の技術書や科学文書で多く用いられているだけでなく、あらゆる出版に適応可能なものです。


## どうしてLaTeXを使うの?
* LaTeXは無料でマルチプラットフォームです。
* LaTeXはテキスト形式（あらゆるテキストエディターで開くことができます）で、ＰＤＦに変換できます。
* LaTeXは、文書本体と、形式の指定を分けています。形式指定を一度すれば、文書本体に集中することができます。
* 作成の流れは、マイクロソフト社のワードに比べて早くできます。
* LaTeXは科学関係の文書編集で広く使われています。
* LaTeXは数式表現において最善の選択枝です。

> LaTeXは、完璧なものではありませんが、習得する価値があります。


## LaTeXの設定

設定は以下のとおりです。

1. *LaTeXディストリビューション*
私はwindows上で、[MiKTeX](https://miktex.org/about) を使っています。
2. *LaTeX エディター*
私は編集が容易にできる[TeXMaker](http://www.xm1math.net/texmaker/) を使っています。もちろん、どんなテキストエディターでもLaTeXファイルを作ったり、編集したりできます。
3. *PDFビューワー* (オプション)
どんなＰＤＦビューワーでも対応可能です。出力結果を見るために使います。

さらに、 [compiler](#追加ツール)を選ぶ必要があります。デフォルトのコンパイラーはpdfLaTeX,です。Unicode や　TTF/OTF フォントを使うシステムでは、LuaLaTeXを使ってください。
もしくは、オンラインシステム（例えば [ShareLaTeX](https://www.sharelatex.com/)）を使ってください。
もっと他の選択枝は[追加ツール](#追加ツール)を参照ください。


## はじめてのLaTeXファイル

では、伝統的な **Hello World** を **LaTeX**で試してみましょう。
もし、 **TexMaker**を使っていれば、まず、`.tex`を拡張しとするファイルを新規作成してください。そして、次のコードを"Hello World!"と出力する次のコードを入力し、"quick build"を実行してください。他のLaTeXエディターでも同じようなことをしてください。

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

TexMakerではこのようになります。:
![](http://i.imgur.com/ZuD5N6U.png)



## さらに詳しく


:eyes:先ほど作成した初めてのLaTeX ファイルを簡単に見てみましょう:
* 第１行目は、インタープリターに、これは**article** 形式で、Ａ４用紙のサイズだと指定しています。他にも **report** 、**book** 形式があります。
* 文書全体は、 **\begin{document}** と **\end{document}** で囲まれています。ここが、文書の心臓部になります。*java* や *C++* の `main()` にあたる部分です。これがなければ、何も表示されません。
* begin と end の間の部分( この例では `Hello World` ) が記述したい部分になります。
* **percent sign** (%) はコメント文です。LaTeXでは無視されます。

#### :zap: 注目！ :zap:

* もう一度、 **\begin{document}** , **\end{document}** , **\documentclass[a4paper]{article}** を確認してください。ある共通パターンに気付くと思います。これらは、**Typesetting Commands** ( 通常 “\”が用いられます。 ) と **arguments** ( “{}”の中に置かれます。 )。 LaTeXは通常のテキストファイルに過ぎませんが、これによって、強力な組版を実現しています。
* このガイドに従っている間は、スムーズにすべてを進めることができます。しかし、将来問題が発生したときも、混乱する必要はありません。人間にも読めるエラーリポートが出力されます。もし、解決できないときも、Googleを使って検索してください。最良の友人となるでしょう。 
* いくつかの文字は **predefined LaTeXにおいて、特別な意味を持つものとして指定されています。もし、そのような文字を出力したいときは、バックスラッシュ(\\)を出力した文字の前に置いてください。**  

![](http://i.imgur.com/9d0bXHH.png)   


## 多言語での使用方法


**ある言語では、うまくいかないかもしれません。TeX を他の言語でつかってみることも、選択肢の一つです。**  

#### :white_check_mark: 第一の方法 :white_check_mark:

第一の方法は ["packages"](#what-is-a-package) に含まれています。（後述します）。例えば、デフォルトのコンパイラーであるpdfLaTeXは、２５６文字の制限があるためです。:  

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

ここでは、 `usepackage[T5]{fontenc}` と `usepackage[utf8]{inputenc}`を使いました。
これは、文書を正しく表示するためのフォントエンコーダーを導入するパッケージを理解するのにとても簡単なものです。もし、TexMaker を使っていれば、上記のコードをコピーするだけです。

![](http://i.imgur.com/UQEewYi.png)

vs パッケージを用いない方法:package::  

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: 中国語・日本語・韓国語を扱う場合、違った方法が必要です。`usepackage{CJKutf8}` を `\begin{CJK}{UTF8}` と `\end{CJK}` と一緒に使ってみるのが手軽な方法です。日本語の例です。 :jp::
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

 :sushi: や :bento:を食べるより簡単です:

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: 第二の方法 :white_check_mark:
他の方法は TeX コンパイラーを [LuaLaTeX](#追加ツール) (もしくは [XeLaTeX](#追加ツール))に変更することです。`fontspec` や `polyglossia`を使えば、ユニコードでもうまく表示できます:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

デフォルトのフォントは (Latin Modern) 全ての文字に対応していません。しかし、`\setmainfont` 行をコメントアウトせずに使用すれば、システムにインストールされているすべてのフォントを使うことができます。 (TTF や OTF フォントが完全にサポートされています。)

## 箇条書き

:straight_ruler: 文章がきちんと整理されていることはとても大切なことです。したがって、あなたが書きたいことを箇条書きに並べてみましょう。
一般的なリストには、**記号付き** と**番号付き** の二つの箇条書きがあります。 どちらのタイプもLaTeX文章では、簡単に扱うことができます:  
* 記号付き箇条書き
記号付き箇条書きでは、 **"itemize"** するだけです。 (平準的な注意向け)
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```  
* 番号付き箇条書き  
番号付き箇条書きでは、 **"enumerate"** する必要があります。 (pun intended)  
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

ここに、二つのタイプのリストがどのように表示されるかを示します:

![](http://i.imgur.com/jzN4RWm.png)


## 段落と節

:blue_book: 節は `\section` で始め、段落は `\paragraph`で始めます。
:orange_book: 小節を`\subsection` で、小段落は `\subparagraph`を加えることで設定できます。

![](http://i.imgur.com/qKbZYnG.png)

## 内容を表にする方法

:metal: 節や小節を `\tableofcontents`で開くことはとても有意義です。

例:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **ヒント**: 改ページをしたいときは `\newpage` を使ってください。



## 脚注

脚注を付けるために、footnote、label、ref　を使えば簡単に設定できます。例えば:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: これは分かりますか？  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **ヒント**: 改行したいときは、`\newline` を使ってください。


## パッケージとは?

LaTeX はデフォルトでたくさんの機能を提供しますが、ある特定のことをするために、パッケージと呼ばれるものを利用する必要があります。LaTeXでパッケージを導入するためには、`\usepackage` と設定するだけです。:package:


ここに、数式を表示するための二つのパッケージを利用している例を示します:

![](http://i.imgur.com/050nrfh.png)  

次の例は回路がどう表示されるかです。:

![](http://i.imgur.com/If4lbLA.png)

:construction: あなたが欲しいと思うパッケージは、Googleで検索してください。例えば、amsmath は数学において広く使われていますし、数学用の拡張機能はたくさんあります。また、circuitikz は回路デザインで使われていいます。この汎用的なガイドでは、それらすべてをカバーすることは不可能です。


## 表組み

実践的な例 :thought_balloon::

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

:star2: 次のように表示されます :star2::

![](http://i.imgur.com/XbZJJ2E.png)

それではもっと詳しく見てみましょう :eyes::

* 表組のために、まず初めに、表組の設定をします。それは、`\begin{table}` と `\end{table}`を使うことです。
* h! について、後ほど画像の章で説明します。表を頁の中央に設定するために `\centering` を使います。
* キャプションは記述のためです。ラベルはタグ付けのためです。画像の章でより詳しく説明します。
* Tabularは最も重要な部分です。表組環境は常にtabular環境を内側に設定する必要があります。
  - `{l|c||r}` の部分は、表の中のフォーマットに関するものです。ここではこのようになります:
    * l か c か r はそれぞれのセル中で、それぞれ左寄せか中央寄せか右寄せかを設定するものです。
    * 縦線 | か || は、表の列の縦線を表しています。
  - 1 & 2 & 3 => 1 2 3 はそれぞれのセルの内容です。& 記号は、行方向にそれぞれの内容がセルに分かれていることを示しています。
  - a `\hline` は、それぞれの行を分ける横線を付け加えるものです。

:bangbang: **ヒント**: より見た目の優れた表組をするためには、booktabs `\usepackage{booktabs}`というパッケージを使うことができます。



## 画像の表示

LaTeXファイルに画像を追加するには、figure環境とgraphicxパッケージが必要です。 `\usepackage{graphicx}` と入力して、

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```
上記のように利用します。
:bangbang: **ヒント**: 文書の幅に対する画像の大きさを [width=\linewidth] で設定します。もし、位置を特定したい場合は、特定の値を設定してください。また、追加した画像は、その名前で参照されます。

```tex
\begin{figure}[h!]
```

:passport_control: Legit 値は:

* h (here) — この場所に設定。
* t (top) — ページの上部に設定。
* b (bottom) — ページの下部に設定。
* p (page) — 別ページで表示に設定。
* ! (override) — 特定の場所に強制設定。

次のように表示されます:

![](http://i.imgur.com/ysY9MOb.png)



## LaTeXへのコード挿入方法

#### :white_check_mark: 最初の方法 :white_check_mark:

プログラマーや開発者にとって、文書の作成において、文章中にコードを挿入できることです。

LaTeXにとって、その過程はシンプルでとても本格的です。あらかじめ用意した文とコードを一緒に表示してみましょう

例:

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

:speech_balloon: **LaTeX はこれらの言語の syntax をサポートしています** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

**{verbatim}** ラッパーを用いることで、シンタックスがどのように整形されるか心配せずに、コードを挿入することができます。いかに、独創的で美しくで本格的に表示できるかを示します。:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: 第２の方法 :white_check_mark: :white_check_mark:

この方法では、より多くの選択肢があります。同一行**inline**に表示したり、形式をカスタムしたり**custom styles** 、特定の言語用**specific language** に設定したり、同じディレクトリ内にある別ファイルから、コードや形式をインポートすることもかのうです。**import code** **from** another **file**。この方法を使うには、**{verbatim}** を使わず、**listings** という名前の:package: を使ってください。

次の例を見てください。:
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
この例から次のことが分かります:

1. コードのブロックを挿入するためには、`\begin{lstlisting}` で始めて　`\end{lstlisting}`　で終わります。
2. 同じディレクトリの別ファイルからコードをインポートする場合は、`lstinputlisiting{name_of_file}`を使います。
3. 言語を指定するためには、 `[language=C++]`を使います。
4. 文中に挿入するためには `\lstinline`を使います。
5. カスタマイズした形式をとるには、`\usepackage{color}` を使い、独自の形式を定義し、自分のテーマに沿ったリストを使います。（下記のコードを参考にしてください）。自分で好きなように設定ができますが、正しいプロパティの名前を調べて使う必要があります。
6. もっと興味があれば？？  [ここ](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

ここに、TexMakerで上記のものをコンパイルする方法を示します。:

![](http://i.imgur.com/XwwDJNo.png)


## LaTeXでの複数ファイル分割方法  

Latexを使っていく上で、文書が長くなりすぎて扱いにくくなるときがあります。そのような場合、ファイルを分割できれば、扱いが簡単になります。

例を見てみましょう
:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

これは、標準的なLaTexファイルです。これを`\input`キーワードを使って、二つのファイルに分割しましょう。:


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

メインのファイルがこれまでと違ってます。しかし、より整理されています。TexMakerでの出力結果がこちらです。:

![](https://camo.githubusercontent.com/e4d46edfad527c4c9be54cf8f1725c2fc52039d6/68747470733a2f2f7331342e706f7374696d672e6f72672f646567306b716875392f6d756c74695f66696c652e706e67)

:bangbang: **ヒント**: 読みやすく、明確で、修正しやすくするために、系統だて、順序だて、論理的にファイルを分割することを高く推奨されています。後で混乱しないように、理由もなく分けることは避けましょう。  

## 追加ツール

#### 配布版

* [MiKTeX](https://miktex.org/about) for Windows.
* [TeX Live](https://www.tug.org/texlive/) for Linux and Unix-based.
* [MacTeX](https://tug.org/mactex/) for macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — an online editor.
* [Overleaf](https://www.overleaf.com/) — an collaborative online editor.
* [StackEdit](https://stackedit.io/) — In-browser markdown editor.

#### LaTeX 編集ソフト

* [TeXMaker](http://www.xm1math.net/texmaker/) Cross platform LaTeX editor.
* [TeXStudio](http://www.texstudio.org/) An enhanced fork of TeXMaker with more features.
* TeXShop and TeXworks (minimal editors)

#### LaTeX コンパイラー

* たいていのエディターには、デフォルトのコンパイラーを変更するオプションがあります。ここにその例をしめします:

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY!!

:tada: 最後までこのガイドを読んでくれてありがとうございます。ここでは、LaTeXの基礎を学んだだけです。 :hammer:  
もっとLaTeX のことを学びたければ、[ここ](http://www.latex-project.org/help/documentation/)を見たり、ウエブで調べてください。

## ライセンス

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
誰でもこのライセンスを有する文章は、コピー、配布、編集が可能です。名前を変更さえすれば、ライセンス自体の改変も可能です。
ライセンス規約の編集も可能です。どうぞご自由に。


<div id='donation'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

あなたの国での一杯のビールのお金で、私の国では、一度の食事ができます。
