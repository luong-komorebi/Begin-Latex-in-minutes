[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
Deutsch ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# Mit LaTeX in Minuten beginnen

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Vorwort:** *Alle Informationen stammen aus meinen Erfahrungen an der Hochschule und aus diversen anderen Quellen. Ich bin weder ein Profi noch ein Experte, sondern ein Student mit einer Leidenschaft für die Software. Jeder kann sich in das Projekt einbringen, entweder, in dem er auf Fehler hinweist, oder selbst einen Pull-Request anfragt. Falls du meine Arbeit unterstützen möchtest, kannst du gerne einen kleinen Beitrag spenden. ([Spenden](#Spenden)).*

### Inhaltsverzeichnis
* [Was ist LaTeX?](#was-ist-latex)
* [Warum sollte ich LaTeX benutzen?](#warum-sollte-ich-latex-benutzen)
* [LaTeX einrichten](#latex-einrichten)
* [Die erste LaTeX-Datei](#die-erste-latex-datei)
* [Mehr Einblicke in LaTeX](#mehr-einblicke-in-latex)
* [Benutzen von mehreren Sprachen](#benutzen-von-mehreren-sprachen)
* [Listen](#listen)
* [Paragrafen und Abschnitte](#paragrafen-und-abschnitte)
* [Ein Inhaltsverzeichnis erstellen](#ein-inhaltsverzeichnis-erstellen)
* [Fußnoten](#fußnoten)
* [Was ist ein Paket?](#was-ist-ein-paket)
* [Tabellen](#tabellen)
* [Bilder einfügen](#bilder-einfügen)
* [Code in LaTeX einfügen](#code-in-latex-einfügen)
* [Mehrere Dateien in LaTeX](#mehrere-dateien-in-latex)
* [Weitere Software](#weitere-software)

## Was ist LaTeX?

LaTeX, ausgesprochen «Lah-tech» oder «Lay-tech» (reimt sich auf «blech»), ist eine Software die ein hochqualitatives Textsatzsystem zur Verfügung stellt. LaTeX wird oft für technische und wissenschaftliche Dokumente eingesetzt, kann jedoch für beinahe jede Form von Veröffentlichungen, von Essays bis hin zu Büchern, verwendet werden.

## Warum sollte ich LaTeX benutzen?

* LaTeX ist frei und für viele Plattformen verfügbar
* LaTeX ist ein einfaches Textdokument, das mit jedem Texteditor geöffnet werden und leicht in ein PDF umgewandelt werden kann
* LaTeX separiert Inhalt und Design. Einmal das Design festlegen, dann auf den Inhalt konzentrieren
* Der Workflow ist schneller verglichen mit MS Word
* LaTeX ist für wissenschaftliche Themen gut geeignet.
* LaTeX ist die beste Lösung wenn es um die Darstellung komplexer mathematischer Formeln geht.

> LaTeX kommt nicht ohne Nachteile, ist es aber trotzdem Wert, erlernt zu werden.

## LaTeX einrichten

Folgendes wird benötigt:


1. *LaTeX Softwarepaket.*
Ich benutze [MiKTeX](https://miktex.org/about) für Windows.
2. *LaTeX Editor.*
Ich benutze [TeXMaker](http://www.xm1math.net/texmaker/) für einfaches bearbeiten, allerdings kann jeder Texteditor LaTeX-Dateien erstellen und ändern.
3. *PDF-Software.* (optional)
Für die Anzeige des fertigen Dokuments ist jede PDF-Software geeignet.

Zusätzlich musst du einen [Kompiler](#weitere-software) wählen. Die Voreinstellung der meisten
Editoren ist pdfLaTeX, aber wenn du Unterstützung für Unicode oder TTF/OTF Fonts benötigst,
benutze LuaLatex.

Oder du benutzt eine Onlinelösung wie [ShareLaTeX](https://www.sharelatex.com/).
Unter [Weitere Software](#weitere-software) findest du eine breitere Auswahl.

## Die erste LaTeX-Datei

Lasst uns ein klassisches **Hello World** in **LaTeX** machen.
Wenn du **TexMaker** installiert hast, erstelle eine neue Datei mit der Endung `.tex`. Dann gib den unten stehenden Code ein um "Hello World!" zu rendern und klicke auf "quick build". In anderen Editoren sollte der Vorgang ähnlich einfach sein.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

Es sollte in TexMaker ungefähr so aussehen:
![](http://i.imgur.com/ZuD5N6U.png)

## Mehr Einblicke in LaTeX

:eyes: Ein genauerer Blick in deine erste LaTex-Datei zeigt:
* Die erste Zeile sagt dem Interpreter, dass du an einem **article** im DIN-A4-Format arbeitest. Zukünftig wirst du sicherlich auch mit **report**, **book** und anderen arbeiten.
* Ein Dokument ist begrenzt mit **\begin{document}** und **\end{document}**. Das ist das Herzstück des Dokuments, vergleichbar mit `main()` in *java* oder *C++*. Ohne diese Zeilen kann das Dokument nicht erstellt werden.
* Der Inhalt zwischen begin und end ( in diesem Fall `Hello World` ) ist dein eigener Inhalt
* Ein **Prozentzeichen** (%) zeigt einen Kommentar an.

#### :zap: Achtung :zap:

* Schau dir nochmal **\begin{document}**, **\end{document}**, **\documentclass[a4paper]{article}** an. Du wirst jetzt das Muster verstehen. Diese Kommandos werden **Typesetting Commands** ( mit vorangestelltem Backslash “\” ) und **arguments** ( innerhalb von geschweiften Klammern “{}” ) genannt. LaTeX stellt genau genommen einfachen Text dar, der durch diese Befehle seine Form erhält.
* Wenn du im Rahmen dieser Anleitung bleibst, solltest du keine Probleme bekommen. Solltest du in der Zukunft auf Probleme stoßen, gilt: **keine Panik**. Die Fehlermeldungen sind verständlich und gut lesbar. Wenn du einen Fehler dadurch auch nicht beheben kannst, hilft eine Suche im Internet oft weiter.  
* Einige Zeichen sind intern für LaTeX reserviert. **Wenn du sie benutzten möchtest, stelle einen Backslash (\) voran um eine korrekte Ausgabe zu garantieren**.  

![](http://i.imgur.com/9d0bXHH.png)   

## Benutzen von mehreren Sprachen

**Einige sprachen funktionieren nicht ohne zusätzliche Konfiguration. Um TeX mit anderen Sprachen zu benutzen hast du ein paar Optionen.**


#### :white_check_mark: Erste Methode :white_check_mark:

Die erste Methode benutzt ["Pakete"](#was-ist-ein-paket) (Du wirst später darüber lesen) weil pdfLaTex, der Standard-Kompiler, auf 256 Zeichen beschränkt ist und einige Kodierungsprobleme hat. Als Beispiel:

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Wir benutzen hier die Packete `usepackage[T5]{fontenc}` und `usepackage[utf8]{inputenc}`. Das ist hier leicht verständlich, die Packete importieren die benötigen Font Kodierer um den Text richtig dar zu stellen. Wenn du TexMaker benutzt wird der obere Code das darstellen:

![](http://i.imgur.com/UQEewYi.png)

gegenüber ohne die Packete zu verwenden :package::  

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: Mit Chinesisch-Japansich-Koreanischen Zeichen zu arbeiten ist etwas verzwickter. Hier macht sich `usepackage{CJKutf8}` mit `\begin{CJK}{UTF8}` und `\end{CJK}` nützlich. Hier ist Japanisch :jp::
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

So einfach wie :sushi: und :bento: zu essen:

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: Zweite Methode :white_check_mark:
Eine andere Methode ist es deinen TeX Kompiler zu [LuaLaTeX](#weitere-software) (oder [XeLaTeX](#weitere-software)) zu wechseln. Nutzt man nun `fontspec` und `polyglossia` funktioniert Unicode ohne weitere Konfiguration:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Das Standardfont (Latin Modern) unterstützt nicht alle Zeichen. Du kannst aber fast alle auf deinem System installierten Fonts benutzen, indem du die `\setmainfont` Zeile auskommentierst. (TTF und OTF Fonts haben volle Unterstützung.)


## Listen

:straight_ruler: Es ist sehr wichtig dein Dokument ordentlich zu halten. Deswegen beginnen wir jetzt damit deine Objekte in Listen zu schreiben.
Die zwei üblichen Typen von Listen sind die **ungeordnete** und die **geordnete** Liste. Beide können mit Leichtigkeit in Latex benutzt werden:
* Ungeordnete Liste 
Ungeordnete Listen benutzen **"itemize"**.
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```  
* Geordnete Liste 
Geordnete Listen brauchen **"enumerate"**.
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

Hier ist die Ausgabe der zwei Listen:

![](http://i.imgur.com/jzN4RWm.png)

## Paragrafen und Abschnitte

:blue_book: Wir beginnen Abschnitte mit `\section` und Paragrafen mit `\paragraph`.
:orange_book: Du kannst auch Unterabschnitte mit `\subsection` und Unterabsätze mit `\subparagraph` erstellen.

![](http://i.imgur.com/qKbZYnG.png)

## Ein Inhaltsverzeichnis erstellen

:metal: Es ist nützlich deine Abschnitte und Unterabschnitte mit einem `\tableofcontents` zu eröffnen

Beispiel:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tipp**: Du kannst `\newpage` benutzen wenn du deine neue Seite beginnen willst.

## Fußnoten

Es ist kinderleicht footnote+label+ref zu benutzen um jederlei Fu0noten zu erstellen. Als Beispiel:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: Siehst du?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tipp**: Du kannst `\newline` benutzen um eine neue Zeile zu beginnen.

## Was ist ein Paket?

LaTeX bietet standardmäßig viele Funktionen, allerdings gibt es Situationen in denen ein so genanntes Packet nützlich ist. Um ein Packet in LaTeX zu importieren musst du nur `\usepackage` benutzen :package:
In diesem Beispiel benutzen wir ein Packet um mathematische Gleichungen zu zeigen:

![](http://i.imgur.com/050nrfh.png)  

Noch eindrucksvoller ist die Ausgabe von Schaltplänen:

![](http://i.imgur.com/If4lbLA.png)

:construction: Du solltest Google benutzen um ein Packet zu finden, dass deinen Anforderungen erfüllt. `asmath` beispielsweise wird oft für mathematische Gleichungen benutzt und hat eine Menge Funktionen, `circuitikz` wird zum designen von Schaltplänen benutzt, etc... Alle Pakete zu erwähnen würde den Rahmen dieser Anleitung sprengen.

## Tabellen

Ein praktisches Beispiel :thought_balloon::

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

:star2: Das ist die Ergebnis :star2::

![](http://i.imgur.com/XbZJJ2E.png)

Nun schauen wir uns das genauer an :eyes::

* Um eine Tabelle zu erstellen brauchen wir erst eine Umgebung dafür, wofür wir `\begin{table}` und `\end{table}` benutzen.
* Über h! wirst du später im "Bilder einfügen"-Teil lernen. Zusammen mit `\centering` hält es die Tabelle in der Mitte der Seite.
* "caption" ist der beschreibende Untertitel. "Label" ist für das markieren. Von beiden wirst du mehr im "Bilder Einfügen"-Teil sehen.
* "tabular" ist der wichtigste Teil. Eine Tabellenumgebung muss immer eine "tabular"-Umgebung beinhalten.
  - In dem Teil `{l|c||r}` formatieren wir den Inhalt der Tabelle. Hier sehen wir:
    * l oder c oder r bedeutet, dass der Inhalt respektive linksbündig, zentriert oder rechtsbündig angeordnet werden soll.
    * Die vertikalen Striche | oder || beschreiben die vertikalen Linien/Ränder der Tabellenspalten.
  - 1 & 2 & 3 => 1 2 3 sind die Inhalte der einzelnen Zellen. Das kaufmännische Und-Zeichen "&" grenzt die Inhalte der Zellen in einer Zeile ab.
  - `\hline` fügt eine horizontale Linie ein um die Zeilen zu separieren.

:bangbang: **Tipp**: Du kannst ein Paket :package: namens booktabs `\usepackage{booktabs}` benutzen für visuell bessere Tabellen.

## Bilder einfügen

Um ein Bild in einer LaTeX Datei einzufügen musst du eine "figure"-Umgebung und das graphicx Packet benutzen. Benutze `\usepackage{graphicx}` und 

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Tipp**: Schreibe [width=\linewidth] um das Bild auf die Breite des Dokuments zu skalieren. Das "fig" wird für spätere Referenzen benutzt, also benenne deine Bilder mit Bedacht. Wenn das Bild im Text gleiten soll, musst du dem "begin" ein bestimmtes Attribut mitgeben:

```tex
\begin{figure}[h!]
```

:passport_control: Erlaubte Attribute sind:

* h (here) — gleiche Stelle
* t (top) — Oben auf der Seite
* b (bottom) — Unten auf der Seite
* p (page) — auf einer separaten Seite
* ! (override) — erzwingt die ausgewählte Stelle

So wird das Bild nun angezeigt:

![](http://i.imgur.com/ysY9MOb.png)

## Code in LaTeX einfügen

#### :white_check_mark: Erste Methode :white_check_mark:

Ein Aspekt der Texterstellung, der für Programmierer und Entwickler von größter Bedeutung ist, ist das professionelle Einfügen von Codes in das Dokument.

Für LaTeX ist der Prozess simple und sehr professionell. Wir umhüllen den Code einfach mit vordefinierten Textstücken und sind fertig.

Beispiel:

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

:speech_balloon: **LaTeX unterstützt die Syntax für diese Sprachen** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

Wie du siehst, kannst du mit **{verbatim}** deinen Code einfach einfügen ohne dir Gedanken über die Syntaxformatierung zu machen. So sieht es ohne weitere Konfiguration aus, sauber und professionell:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Zweite Methode :white_check_mark: :white_check_mark:

Diese Methode gibt dir mehr Einstellungsmöglichkeiten, einschließlich das Einfügen von Code **inline**, einen **eigenen Code-Stil** erstellen, eine **spezifische Sprache** für den Code wählen, **Code** von einer anderen **Datei** im selben Verzeichnis zu **importieren**... Mit dieser Methode benutzt du nicht **{verbatim}**, sondern importierst das Paket :package: mit dem Namen **listings**.

Folgendes dient als Beispiel:
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
Aus dem Beispiel erkennen wir:

1. Um einen Codeblock einzufügen starten man mit `\begin{lstlisting}` und endet mit `\end{lstlisting}`
2. Um Code aus einer anderen Datei im selben Verzeichnis zu importieren benutzt man `lstinputlisiting{name_of_file}`
3. Um eine Sprache für den Code fest zu legen benutzt man `[language=C++]`
4. Um Code inline einzufügen benutzt man `\lstinline`
5. Um einen eigenen Code-Stil zu erstellen wird das `\usepackage{color}` importiert und der eigene Stil definiert, dann legt man den zu benutzenden Stil für das Objekt fest (Bitte schaue die Dokumentation hier drunter an). Man kann viele Dinge selbst definieren, in der Dokumentation findet man dafür die richtigen Namen der Eigenschaften.
6. Interessiert? Mehr gibt es [hier](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Hier ist die Ausgabe des oberen Codes in TexMaker:

![](http://i.imgur.com/XwwDJNo.png)

## Mehrere Dateien in LaTeX

Wenn wir LaTeX benutzen kann es vorkommen, dass das Dokument zu lang ist um es zu verarbeiten. Deswegen sollten wir die Datei aufteilen, damit der Inhalt leichter zu bearbeiten ist.

Sehen wir uns ein Beispiel an:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

Das ist nur eine normale LaTeX Datei. Nun lasst uns die Datei in zwei Zeile aufteilen, dazu benutzen wir `\input`:


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

Jetzt sieht die Hauptdatei anders aus, kann aber besser dokumentiert werden. Hier ist das Ergebnis in TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Tipp**: Für die Lesbarkeit, Deutlichkeit und für Wartungszwecke wird nahegelegt, dass die Hauptdatei systematisch, hierarchisch und wissenschaftlich eingeteilt wird. Teile die Datei nicht grundlos, da es sonst zu einem Durcheinander kommen kann.

## Weitere Software

#### Softwarepakete

* [MiKTeX](https://miktex.org/about) für Windows.
* [TeX Live](https://www.tug.org/texlive/) für Linux und Unix-basierte Systeme.
* [MacTeX](https://tug.org/mactex/) für macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — ein Online-Editor.
* [Overleaf](https://www.overleaf.com/) — ein kollaborativer Online-Editor.
* [StackEdit](https://stackedit.io/) — browserbasierter Editor auf Markdown-Basis.

#### LaTeX Editoren

* [TeXMaker](http://www.xm1math.net/texmaker/) LaTeX-Editor (Multiplattform).
* [TeXStudio](http://www.texstudio.org/) Ein verbesserter Fork von TeXMaker mit mehr Funktionen.
* TeXShop und TeXworks (minimalistische Editoren)

#### LaTeX Compiler

* Die meisten Editoren haben eine Option um den Standard-Kompiler zu ändern. Hier ein Beispiel:

![](http://i.imgur.com/FbNUiL7.png)

## Hurrah!!

:tada: Danke, dass du diese Anleitung gelesen hast. Du weißt jetzt alles, um mit LaTeX zu beginnen. :hammer:  
Wenn du noch mehr wissen möchtest, ist [hier](http://www.latex-project.org/help/documentation/) ein guter Einstiegspunkt.

## Lizenz

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION: You just DO WHAT THE FUCK YOU WANT TO.  



<div id='Spenden'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

Ein Bier in deinem Land kostet soviel wie eine Mahlzeit in meinem Land.
