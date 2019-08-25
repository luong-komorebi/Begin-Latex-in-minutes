[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
Français ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# LaTeX en quelques minutes

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Note:** *Tout ce qui est écrit dans ce guide vient de ma propre expérience et des articles que j'ai lu. Je ne suis pas un professionnel ou expert, mais un étudiant qui apprécie beaucoup ce langage. N'importe qui peut ouvrir une discussion dans la section "issue", ou faire une "pull request". Si vous appréciez mon travail, vous pouvez me faire une [donation](#donation).*

### Sommaire
* [Qu'est ce que LaTeX?](#qu-est-ce-que-latex)
* [Pourquoi utiliser LaTeX?](#pourquoi-utiliser-latex)
* [Installation de LaTeX](#installation-de-latex)
* [Premier document LaTeX](#premier-document-latex)
* [Un regard plus attentif](#un-regard-plus-attentif)
* [Multilangue](#multilangue)
* [Listes](#listes)
* [Paragraphes et sections](#paragraphes-et-sections)
* [Faire un sommaire](#faire-un-sommaire)
* [Notes de bas de page](#notes-de-bas-de-page)
* [Les packages](#les-packages)
* [Table](#table)
* [Ajouter des images](#ajouter-des-images)
* [Insérer du code](#insérer-du-code)
* [Travailler sur plusieurs documents](#travailler-sur-plusieurs-documents)
* [Outils supplémentaires](#outils-supplémentaires)

## Qu est ce que LaTeX?

LaTeX, pronnoncé «Lah-tech», est un langage et un système de composition de documents. Il est essentiellement utilisé pour les documents scientifiques plutôt technique, mais peut être utilisé pour toute forme de publication.

## Pourquoi utiliser LaTeX?

* LaTeX est gratuit et multiplateforme.
* LaTeX est juste un document texte (qui peut être ouvert avec n'importe quel éditeur de texte), facilement convertissable en PDF.
* LaTeX sépare le contenu du style.
* Très simple d'utilisation.
* LaTeX est très utilisé pour les articles scientifiques.
* LaTeX est la meilleure option quand il faut écrire des expressions mathématiques.

> LaTeX possède tout de même quelques inconvénients, mais ce n'est rien à côté de ce qu'il permet de faire

## Installation de LaTeX

Vous allez avoir besoin de:


1. *Une distribution LaTeX.*
J'utilise [MiKTeX](https://miktex.org/about) pour Windows.
2. *Un éditeur.*
J'utilise [TeXMaker](http://www.xm1math.net/texmaker/) pour éditer simplement, mais tout éditeur de texte fonctionne avec LaTeX.
3. *Un lecteur PDF.* (optionnel)
N'importe quel lecteur de PDF fera l'affaire. Il s'agit juste de pouvoir afficher le résultat.

Il vous faut également un [compilateur](#additional-tools). Le compilateur par défaut de la plupart des éditeurs est pdfLaTeX, mais si vous utilisez les formats de polices TTF/OTF, utilisez LuaLaTeX.

Si vous préférez, vous pouvez utiliser un éditeur en ligne, comme [ShareLaTeX](https://www.sharelatex.com/).
Allez jetter un oeil aux [Outils supplémentaires](#outils-supplémentaires) pour d'autres suggestions.

## Premier document LaTeX

Commençons par le fameux **Hello World**.
Si vous avez intallé **TexMaker**, commencez par créer un nouveau fichier portant l'extension `.tex`. Puis, insérez-y le code ci dessous pour afficher "Hello World!" et cliquez sur "quick build". Pour d'autres éditeurs, la procédure devrait être similaire.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % Ceci est votre contenu

\end{document}
```

Le résultat devrait être le suivant:
![](http://i.imgur.com/ZuD5N6U.png)

## Un regard plus attentif

:eyes: Regardons en détails votre premier document LaTex :
* La première ligne indique à votre interpréteur que vous travaillez sur un **article** de taille a4. Vous pourrez être amené à travailler sur d'autres formats de documents, comme **report** et **book**.
* Les lignes **\begin{document}** et **\end{document}** indiquent le début et la fin du document. Le contenu joue le même rôle que le `main()` en *java* ou *C++*. Sans ces deux lignes, le document ne peut pas être compilé.
* Ce qui se trouve entre ces deux lignes (ici "Hello World!") est tout simplement votre contenu.
* Le symbole **pourcentage** (%) indique un commentaire, que LaTeX va ignorer.

#### :zap: Attention :zap:

* Regardez bien **\begin{document}** , **\end{document}** , **\documentclass[a4paper]{article}** .Vous devez avoir remarqué le pattern. On les appellent **Typesetting Commands** ( précédées d'un “\” ) et **arguments** ( placés entre accolades “{}” ). LaTeX est en fait du texte brut mis en forme via ces commandes.
* Dans ce guide, tout fonctionnera bien. Si dans le futur vous rencontrez des problèmes, **ne paniquez pas !**. Les messages d'erreurs sont très compréhensibles. Et si vous ne trouvez pas votre erreur, Google est votre ami.  
* Certains caractères ont **un sens précis en LaTeX. Vous devez utiliser des antislashs (\\) devant ceux ci pour pouvoir les afficher dans un texte.**  

![](http://i.imgur.com/9d0bXHH.png)   

## Multilangue

**Certains langages ne sont pas directement supportés.**  

#### :white_check_mark: Première méthode :white_check_mark:

Elle consiste à installer des ["packages"](#what-is-a-package) (Vous allez voir ça après) car pdfLaTeX, le compilateur par défaut, est limité à 256 caractères et quelques encodages. Par exemple:  

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. Ceci est le "hello world" Vietnamien.

\end{document}
```

Ici, nous utilisons les packages `usepackage[T5]{fontenc}` et `usepackage[utf8]{inputenc}`. Les packages importent ce qu'il faut pour afficher ce contenu correctement. Si vous utilisez TexMaker voici le résultat de ce code avec les packages :

![](http://i.imgur.com/UQEewYi.png)

et sans les packages :package::  

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: Écrire en Chinois, Japonais, ou Coréen peut s'avérer délicat en général. Ici, `usepackage{CJKutf8}`, `\begin{CJK}{UTF8}` et `\end{CJK}` gèrent ça très bien !. Voici du japonais :jp: :
```tex
\documentclass[a4paper]{article}
\usepackage{CJKutf8}

\begin{document}

\begin{CJK}{UTF8}{min}
この記事を読んでいただきありがとうございます。
%Merci d'avoir lu cet article.
\end{CJK}

\end{document}
```

Aussi simple que manger des :sushi: et des :bento: :

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: Seconde méthode :white_check_mark:
Une autre méthode est de remplacer le compilateur TeX par [LuaLaTeX](#additional-tools) (ou [XeLaTeX](#additional-tools)). Il suffit alors d'utiliser `fontspec` et `polyglossia`:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. Ceci est le "hello world" Vietnamien.

\end{document}
```

La police par défaut (Latin Modern) ne supporte pas tous les caractères. Mais vous pouvez utiliser n'importe quelle police installée sur votre ordinateur, en décommentant `\setmainfont`. (Les polices de type TTF et OTF sont entièrement supportées)


## Listes

:straight_ruler: L'organisation de votre document est très importante. Alors, rangeons vos éléments dans une liste.  
Les deux types communs de listes sont **non ordonnées** et **ordonnées**. Ces deux types sont pris en charge par LaTeX :  
* non ordonnées
Les listes non ordonnées ont seulement besoin de **"itemize"**.
```tex
\begin{itemize}
\item Un élement.
\item Un autre élement.
\end{itemize}
```  
* ordonnées
Les listes ordonnées, cependant, utilisent **"enumerate"**.  
```tex
\begin{enumerate}
\item Premier élément.
\item Second élément.
\end{enumerate}
```

Voici le rendu des deux listes :

![](http://i.imgur.com/jzN4RWm.png)

## Paragraphes et sections

:blue_book: Une section commence par `\section` et un paragraphe par `\paragraph` .
:orange_book: Il est possible de créer des sous sections avec `\subsection` et des sous paragraphes avec `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Faire un sommaire

:metal: Il est essentiel de pouvoir naviguer à travers les sections ou sous sections à l'aide d'un sommaire (`\tableofcontents`).

Example:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Astuce** : Vous pouvez utiliser `\newpage` pour faire une nouvelle page.

## Notes de bas de page

C'est très simple d'utiliser footnote+label+ref pour faire des notes en bas de page. Par exemple:
```tex
Salut, laissez moi me présenter\footnote{\label{myfootnote}Hello footnote}.
... (plus bas)
Je fais référence à moi même \ref{myfootnote}.
```
:point_down: :point_down: Vous voyez ?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Astuce** : Vous pouvez utiliser `\newline` pour aller à la ligne.

## Les packages

LaTeX contient beaucoup de fonctionnalités par défaut, mais il est parfois utile d'utiliser des packages. Pour importer un package en LaTeX, ajoutez simplement `\usepackage` :package:

Voici un exemple d'utilisation de deux packages pour les mathématiques:

![](http://i.imgur.com/050nrfh.png)  

Mieux encore, l'affichage de circuits électriques:

![](http://i.imgur.com/If4lbLA.png)

:construction: Pour trouver des packages, faites une recherche sur Google. Par exemple, amsmath est très utilisé pour les maths et possède beaucoup d'extensions. Les passer tous en revue dans ce guide est chose impossible ..

## Table

Exemple :thought_balloon: :

```tex
\begin{table}[h!]
  \centering
  \caption{Description de la table.}
  \label{tab:table1}
  \begin{tabular}{l|c||r}
    1 & 2 & 3\\
    \hline
    a & b & c\\
  \end{tabular}
\end{table}
```

:star2: Voici le rendu :star2: :

![](http://i.imgur.com/XbZJJ2E.png)

Maintenant, regardons plus en détails :eyes: :

* Pour chaque table, nous devons d'abord définir un environnement avec `\begin{table}` et `\end{table}` .
* Vous découvrirez `h!` plus tard dans la partie image. Il va avec `\centering` pour garder la table centrée sur la page.
* `Caption` est utilisé pour la description. `Label` pour nommer la table.
* `Tabular` est la partie la plus importante. Un conteneur table a toujours besoin d'un environnement `tabular`.
  - La partie `{l|c||r}` concerne le formatage de la table. Ici, on peut voir :
    * l ou c ou r qui indique que le contenu de chaque cellule est left-aligned (aligné à gauche) ou center-aligned (aligné au centre) ou right-aligned (aligné à droite), respectivement.
    * la barre verticale | ou || est en réalité le format des lignes verticales des colonnes de la table.
  - 1 & 2 & 3 => 1 2 3 sont les contenus de chaque cellules. `&` est utilisé pour séparer le contenu de chaque cellule.
  - a `\hline` ajoute une ligne horizontale pour séparer chaque ligne de la table.

:bangbang: **Astuce** Vous pouvez utiliser le package :package: booktabs `\usepackage{booktabs}` pour un meilleur visuel.

## Ajouter des images

Pour ajouter une image au document LaTeX, il faut utiliser un environnement `figure` et le package graphicx. Utilisez `\usepackage{graphicx}` et

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{De quoi est-il question?}
  \label{fig:unlabel}
\end{figure}
```

:bangbang: **Astuce**: Ajoutez [width=\linewidth] pour mettre l'image à l'échelle du document. La mention `fig` est utilisée pour référencer l'image plus tard. Choisissez donc la avec précaution.

```tex
\begin{figure}[h!]
```

:passport_control: Les valeurs autorisées sont :

* h (here) - au même endroit
* t (top) - en haut de page
* b (bottom) - en bas de page
* p (page) - sur un autre page
* ! (override) - va forcer la localisation spécifiée

Voici le rendu de l'image :

![](http://i.imgur.com/ysY9MOb.png)

## Insérer du code

#### :white_check_mark: Première méthode :white_check_mark:

Un aspect extrèmement important pour les développeurs dans un compilateur de texte est l'insertion de code dans le document.

En LaTeX, le processus est très simple et professionnel. Il suffit juste de placer le code source dans un environnement particulier.

Exemple :

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

:speech_balloon: **LaTeX supporte la syntaxe des langages suivant** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

Comme vous pouvez le voir, avec l'utilisation de **{verbatim}** vous pouvez insérer du code dans votre document sans vous souciez du formatage. Voici le rendu :

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Seconde méthode :white_check_mark: :white_check_mark:

Cette méthode vous donne plus d'options, comme l'insertion de code **inline**, **personnaliser le style**, choisir un **langage spécifique**, **importer du code** d'un autre fichier du même répertoire, ... Cette méthode n'utilise pas **{verbatim}** mais un package :package: appelé **listings**.

Prenons l'exemple suivant :
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
Vous pouvez voir que:

1. Pour insérer un bloc de code, commencez par `\begin{lstlisting}` et terminez avec `\end{lstlisting}`
2. Pour importer du code d'un fichier du même répertoire, il faut utiliser `lstinputlisiting{name_of_file}`
3. Spéficier le langage se fait avec `[language=C++]`
4. `\lstinline` permet l'insertion de code inline
5. Pour appliquer un style particulier, il faut utiliser `\usepackage{color}` et définir votre style, puis définir votre thème sous forme de liste (Exemple dans le code ci-dessus). Il est possible de customiser beaucoup de choses, mais vous aurez besoin de regarder la documentation pour connaître les noms des propriétés.
6. Intéressé ?? Voir [ici](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Voici le rendu du code au dessus, compilé avec TexMaker:

![](http://i.imgur.com/XwwDJNo.png)

## Travailler sur plusieurs documents

Un problème potentiel en LaTeX peut être la longueur du document. Pour faire face à cette situation, vous pouvez diviser le contenu du document en plusieurs fichiers pour que le contenu soit plus facilement manipulable.

Regardons cet exemple:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Salut Latex, c'est la partie 1.

Salut Latex, c'est la partie 2.

\end{document}
```

C'est un simple fichier LaTeX. Maintenant, divisons le en deux parties, en utilisant le mot clé `\input`:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Salut Latex, c'est la partie 1.

\input{second_file}

\end{document}
```


```tex
% second_file.tex
Salut Latex, c'est la partie 2.
```

Le fichier principal est différent, mais mieux organisé. Voici le résultat avec TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Astuce** : Pour plus de clareté et de maintenabilité, il est fortement recommandé de diviser systématiquent le fichier principal, de manière hiérachique. Cependant, ne divisez pas sans raison, ou vous pourriez être perdu par la suite.  

## Outils supplémentaires

#### Distributions

* [MiKTeX](https://miktex.org/about) pour Windows.
* [TeX Live](https://www.tug.org/texlive/) pour Linux et dérivés.
* [MacTeX](https://tug.org/mactex/) pour macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — un éditeur en ligne.
* [Overleaf](https://www.overleaf.com/) — un éditeur collaboratif en ligne.
* [StackEdit](https://stackedit.io/) - éditeur markdown en ligne.

#### Éditeurs LaTeX

* [TeXMaker](http://www.xm1math.net/texmaker/) éditeur LaTeX multiplateforme.
* [TeXStudio](http://www.texstudio.org/) Une amélioration de TeXMaker avec plus de fonctionnalités.
* TeXShop et TeXworks (éditeurs basiques)

#### Compilateurs LaTeX

* La plupart des éditeurs possèdent une option pour changer le compilateur par défaut. Exemple:

![](http://i.imgur.com/FbNUiL7.png)

## HOURRA !!

:tada: Merci d'avoir terminé ce guide. Voici plus ou moins tout ce que vous devez connaître à propos de LaTeX. :hammer:  
Si vous êtes vraiment intéressé, vous trouverez plus de LaTeX [ici](http://www.latex-project.org/help/documentation/) ou tout simplement sur le web.

## Licence

[![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Tout le monde est autorisé à copier et distribuer des copies originelles ou modifiées de ce document, et le changement est autorisé tant que le nom est modifié.   
TERMES ET CONDITIONS DE COPIE, DE DISTRIBUTION ET DE MODIFICATION : juste DO WHAT THE FUCK YOU WANT (FAITES CE QUE VOUS VOULEZ)


<div id='donation'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

Une bière dans votre pays équivaut à un repas dans le mien.
