[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
Polski

---

# Szybki start w Latex

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Adnotacja** _Zawartość tego poradnika oparta jest na doświadczeniach autora - studenta, który czerpie przyjemność z tego co robi. Jeśli widzisz miejsce na poprawę - proszę stwórz incydent lub pull request. Jeśli ten dokument stawowi dla Ciebie dużą wartość, proszę, rozważ [darowiznę dla autora](#donation)._

### Spis treści

- [Czym jest Latex?](#czym-jest-latex)
- [Dlaczego miałbym go używać?](#dlaczego-miałbym-go-używać)
- [Konfiguracja](#konfiguracja)
- [Pierwsze kroki](#pierwsze-kroki)
- [Rzut oka na szczegóły](#Rzut-oka-na-szczegóły)
- [Wiele języków w jednym dokumencie](#Wiele-języków-w-jednym-dokumencie)
- [Listy i wypunktowania](#listy-i-wypunktowania)
- [Ustępy i rozdziały](#Ustępy-i-rozdziały)
- [Tworzenie spisu treści](#tworzenie-spisu-treści)
- [Przypisy](#przypisy)
- [Co to jest pakiet?](#co-to-jest-pakiet)
- [Tabele](#tabele)
- [Dodawanie obrazów](#dodawanie-obrazów)
- [Wstawianie kodu w dokument Latex](#wstawianie-kodu-w-dokument-latex)
- [Praca na wielu plikach w Latex](#Praca-na-wielu-plikach-w-Latex)
- [Przydatne narzędzia](#przydatne-narzędzia)

## Czym jest Latex?

LaTeX (wymawiane jako Latech) to system do zautomatyzowanego przygotowywania dokumentów. Znajduje swoje zastosowanie głównie wśród środowisk naukowych oraz przy dużych publikacjach, chociaż można go z powodzeniem wykorzystywać do dowolnych celów wydawniczych.

## Dlaczego miałbym go używać?

- LaTeX jest darmowy, działa na większości dostępnych platform.
- Pliki LaTeX mogą zostać otwarte za pomocą każdego edytora tekstu, a następnie przekonwertowane do PDF.
- LaTeX rozdziela formę i treść. Do raz określonej formy możemy dodawać kolejną treść.
- Przepływ pracy jest znacząco szybszy niż w MS Word.
- LaTeX cieszy się dużym zaufaniem środowisk naukowych.
- LaTeX jest po prostu najlepszy, gdy w Twoim dokumencie pojawia się matematyka.

> LaTeX nie jest pozbawiony wad, ale nadal warto się go nauczyć.

## Konfiguracja

Będziesz potrzebować:

1. _Dystrybucja LaTeX._
   Korzystam z [MiKTeX](https://miktex.org/about) for Windows.
2. _Edytor tekstu dla LaTeX._
   Korzystam z [TeXMaker](http://www.xm1math.net/texmaker/) by ułatwić sobie pracę, chociaż pliki LaTeX możesz edytować nawet w Notatniku.
3. _Oprogramowanie do wyświetlania PDF._ (optional)
   Może być dosłownie dowolny.

Dodatkowo musisz dobrać [kompilator](#przydatne-narzędzia). Domyślnym kompilatorem w większości edytorów jest pdfLaTeX, ale może się zdarzyć, że będziesz potrzebować wsparcia dla fontów TTF/OTF - godnym polecenia jest wtedy LuaLaTex.

Możesz również zdecydować się na gotowe rozwiązania internetowe, takie jak np. [ShareLaTeX](https://www.sharelatex.com/).
Zajrzyj do sekcji [Przydatne narzędzia](#przydatne-narzędzia) by poznać alternatywy.

## Pierwsze kroki

Zacznijmy od tradycyjnego **Hello World** w **LaTeX**.
Po tym jak zainstalowałeś **TexMaker**, stwórz plik z rozszerzeniem `.tex`. Następnie przepisz do edytora tekst poniżej, by wyświetlić "Hello World!" i uruchom "quick build". W innych edytorach ta procedura nie powinna się znacząco różnić.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

Tak powinno to wyglądać w TexMaker
![](http://i.imgur.com/ZuD5N6U.png)

## Rzut oka na szczegóły

:eyes: Wyjaśnimy sobie co właśnie napisaliśmy:

- Pierwsza linia mówi kompilatorowi, że pracujemy na klasie **article** o wymiarach kartki A4. Istnieją inne klasy dokumentów, na których możesz pracować - o ich istnieniu możesz przeczytać w dokumentacji LaTeX.
- Dokument rozpoczyna się **\begin{document}** a kończy **\end{document}**. Pomyśl o tym jak o sercu dokumentu, czymś jak `main()` w _java_ lub _C++_... bez którego dokument nie może zostać wyrenderowany.
- Wszystko pomiędzy znacznikami begin i end to zawartość dokumentu.
- **Znak procenta** (%) oznacza komentarz, który nie jest brany pod uwagę przy renderowaniu.

#### :zap: Uwaga! :zap:

- Gdy spojrzysz na znaczniki **\begin{document}**, **\end{document}**, **\documentclass[a4paper]{article}** możesz zauważyć pewną właściwość. Są to **Polecenia składni** ( zwyczajowo poprzedzane znakiem “\” ) i **argumenty** ( osadzane między nawiasami klamrowymi “{}”, gdy są obowiązkowe lub między nawiasami kwadratowymi "[]", gdy są opcjonalne). To właśnie tego typu polecenia napędzają LaTeX.
- Jeśli uważnie prześledziłeś wszystkie kroki nie powinieneś napotkać żadnych problemów. Niemniej, jeśli w przyszłości natrafisz na błędy - nie panikuj. Błędy są napisane w czytelny sposób i mogą zostać rozwiązane samodzielnie lub z pomocą Google.
- Niektóre znaki są **zastrzeżone w LaTeX. By ich użyć będziesz potrzebował backslasha (\\) przed każdym z nich.**

![](http://i.imgur.com/9d0bXHH.png)

## Wiele języków w jednym dokumencie

**Niestety, nie wszystkie języki działają poprawnie w LaTeX od razu po instalacji, czasem trzeba im pomóc.**

#### :white_check_mark: Pierwszy sposób :white_check_mark:

Pierwszą metodą jest wykorzystanie ["pakietu"](#co-to-jest-pakiet) (Przeczytasz o tym później), ponieważ domyślny kompilator pdfLatex jest ograniczony do 256 znaków co powoduje problemy z kodowaniem. Na przykład:

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

W tym przypadku korzystamy z pakietu `usepackage[T5]{fontenc}` oraz `usepackage[utf8]{inputenc}`. Ta paczka pomoże kompilatorowi wyświetlić poprawnie tekst. Jeśli korzystasz z TexMaker to powinieneś zobaczyć taki efekt:

![](http://i.imgur.com/UQEewYi.png)

jeśli jednak usuniesz ten pakiet :package: z tekstu zobaczysz to:

![](http://i.imgur.com/xvzrQX2.png)

:umbrella: W prosty sposób możesz poradzić sobie ze znakami języków dalekowschodnich za pomocą `usepackage{CJKutf8}` z `\begin{CJK}{UTF8}` i `\end{CJK}`. Poniżej próbka tego pakietu w języku japońskim :jp::

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

To proste niczym zjedzenie :sushi::

![](http://i.imgur.com/vAN1WUi.png)

#### :white_check_mark: Kolejny sposób :white_check_mark:

Kolejna metoda zakłada, że korzystasz z kompilatora [LuaLaTeX](#przydatne-narzędzia) (lun [XeLaTeX](#przydatne-narzędzia)). Za pomocą `fontspec` i `polyglossia` kodowanie Unicode zadziała _out of the box_:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Domyślny font (Latin Modern) nie wspiera wszystkich znaków. Niemniej, możesz skorzystać z dowolnego fonta zainstalowanego na Twoim komputerze usuwając znak komentarza z lini `\setmainfont`.

## Listy i wypunktowania

:straight_ruler: To bardzo ważne, by panować nad porządkiem w Twoim dokumencie. Z tego powodu postarajmy się zająć listami.  
Dwoma najpopularniejszymi listami są listy **numerowanie** i **nienumerowane**. Obie z nich możemy bez problemu zastosować w LaTeXu:

- Lista nienumerowana  
  Lista nienumerowana potrzebuję tylko **itemize**

  <!-- I wasnt able to translate that pun, sorry -->

```tex
\begin{itemize}
\item Element listy.
\item Kolejny element listy.
\end{itemize}
```

- Lista numerowana  
  Lista numerowana potrzebuje wartości **enumerate**.

    <!-- this one too -->

```tex
\begin{enumerate}
\item Element listy.
\item Kolejny element listy.
\end{enumerate}
```

Oto jak prezentują się oba rodzaje list.

![](http://i.imgur.com/jzN4RWm.png)

## Ustępy i rozdziały

:blue_book: Rozdział rozpoczynamy komendą `\section`, a ustępy za pomocą `\paragraph`.
:orange_book: Możesz tworzyć również podrozdziały `\subsection` oraz podustępy `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Tworzenie spisu treści

:metal: Spis treści wygeneruje się automatycznie za każdym razem, gdy umieścisz w pliku komendę `\tableofcontents`

Przykład:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Wskazówka**: by stworzyć nową stronę użyj komendy `\newpage`.

## Przypisy

Bardzo prosto możesz stworzyć przypisy, do których możesz się potem odnosić. Na przykład:

```tex
Pozwól, że się przedstawię!\footnote{\label{myfootnote}Witaj Przypisie!}.
... (później)
Odnoszę się do siebie \ref{myfootnote}.
```

:point_down: :point_down: Widzisz jakie to proste? ? :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Wskazówka**: Nową linie stworzysz za pomocą `\newline`.

## Co to jest pakiet?

LaTeX przychodzi z kompletem całkiem ciekawych funkcji, niemniej czasem potrzebujemy nieszablonowego rozwiązania, które dostarcza pakiet. By zaimportować pakiet do LaTeXa wystarczysz, że umieścisz `\usepackage` przed rozpoczęciem dokumentu :package:

Spójrz proszę na poniższy przykład dla pakietu obsługującego równania:

![](http://i.imgur.com/050nrfh.png)

Albo na jeszcze bardziej imponujące obwody elektroniczne:

![](http://i.imgur.com/If4lbLA.png)

:construction: By znaleźć pakiety, których potrzebujesz użyj Google - ich liczebność oraz kompleksowość przerosłaby dowolnej wielkości poradnik.

## Tabele

Prosty przykład :thought_balloon::

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

:star2: Zwróci nam coś takiego :star2::

![](http://i.imgur.com/XbZJJ2E.png)

Przyjrzyjmy się temu bliżej :eyes::

- W tabelach pierwsze czego potrzebujemy to środowisko tabeli, dlatego używamy poleceń `\begin{table}` i `\end{table}`.
- O tym co oznacza h! dowiesz się później w sekcji poświęconej obrazom. Komenda `\centering` utrzymuje tabelę na środku strony.
- _Caption_ to podpis. _Label_ służy do oznaczania tabeli. O tym też dowiesz się w sekcji poświęconej obrazom.
- _Tabular_ jest najważniejszym elementem. Środowisko tabeli (_table_) wymaga, by w środku znajdowało się środowisko _tabular_.
  - fragment `{l|c||r}` opisuje formatowanie tabeli.
    - l lub c lub r oznacza, że zawartość każdej komórki zostanie wyrównana do lewej/środkowej/prawej strony (zgodnie z angielskim _left_, _center_, _right_).
    - Pionowa kreska | albo || oznacza sposób rozgraniczania kolumn.
  - 1 & 2 & 3 => 1 2 3 to zawartość z każdej komórek. Znak & oddziela każdą z komórek.
  - `\hline` dodaje poziomą linię rozgraniczającą wiersze.

:bangbang: **Wskazówka**: Skorzystaj z pakietu :package: booktabs `\usepackage{booktabs}`, by tworzyć efektowne tabele.

## Dodawanie obrazów

By dodać obraz w LaTeXu potrzebujesz środowiska _figure_ oraz pakietu graphicx. Umieść `\usepackage{graphicx}` w preambule oraz poniższy kod w treści dokumentu

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Wskazówka**: Umieść [width=\linewidth] by przeskalować obraz do szerokości dokumentu. Jeśli chcesz, by dokument opływał zdjęcie musisz dodać do niego argument określający jego pozycję. W tym przypadku również możesz oznaczyć ten element za pomocą komendy _label_.

```tex
\begin{figure}[h!]
```

:passport_control: Poprawne wartości to:

- h (_here_) — dokładnie to miejsce
- t (_top_) — góra strony
- b (_bottom_) — dół strony
- p (_page_) — dodatkowa strona
- ! (_override_) — wymusi wskazaną lokalizację

W ten sposób wyrenderuje się nasze zdjęcie:

![](http://i.imgur.com/ysY9MOb.png)

## Wstawianie kodu w dokument Latex

#### :white_check_mark: Pierwszy sposób :white_check_mark:

Kluczowym aspektem dla wielu programistów jest to jak profesjonalne wkleić kod do ich dokumentów.

W LaTeXu ten aspekt nie stanowi żadnego problemu.

Przykład:

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

:speech_balloon: **LaTeX wspiera składnię następujących języków** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

Jak widzisz, za pomocą znaczników **{verbatim}** możesz wkleić swój kod do dokumentu nie przejmując się jego formatowaniem. Spójrz jak profesjonalnie to wygląda:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Drugi sposób :white_check_mark: :white_check_mark:

Ten sposób pozwala na trochę więcej, w tym wstawianie kodu wewnątrz linii, personalizowane formatowanie kodu, dobór konkretnego języka, import kodu z innego pliku. W tym sposobie korzytać z pakietu :package: o nazwie **listings**.

Spójrz na poniższy przykład:

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

Wyciągnijmy kilka wniosków:

1. By wstawić blok kodu zacznij go od `\begin{lstlisting}`, a skończ na `\end{lstlisting}`
2. By zaimportować treść z innego pliku użyj komendy `lstinputlisiting{name_of_file}`
3. By określić język użyj `[language=C++]`
4. By wstawić kod w obrębie linii użyj `\lstinline`
5. By zaaplikować własne style skorzystaj z `\usepackage{color}` i zdefiniuj własne style (spórzj na przykład). Możesz modyfikować szeroki wachlarz stylów, ale pamiętaj by wspomagać się dokumentacją.
6. Więcej informacji znajdziesz [tutaj](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Właśnie tak to się wyświetla:

![](http://i.imgur.com/XwwDJNo.png)

## Praca na wielu plikach w Latex

Z czasem, gdy pracujemy w LaTeXu nasze pliki rosną do niewygodnych rozmiarów, wymuszając na nas rozdzielenie tego na komponenty.

Spójrzmy na to:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

Tak zapisywaliśmy to do tej pory. Teraz podzielmy to na pliki i zaimportujmy je za pomocą `\input`:

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

Główny plik wygląda teraz inaczej, ale jest z pewnością lepiej zorganizowany.

![](https://camo.githubusercontent.com/e4d46edfad527c4c9be54cf8f1725c2fc52039d6/68747470733a2f2f7331342e706f7374696d672e6f72672f646567306b716875392f6d756c74695f66696c652e706e67)

:bangbang: **Wskazówka**: Dla czytelności i świetego spokoju edytujacego zaleca się, by podzielić Twój plik systematycznie i metodycznie.

## Przydatne narzędzia

#### Dystrybucje

- [MiKTeX](https://miktex.org/about) for Windows.
- [TeX Live](https://www.tug.org/texlive/) for Linux and Unix-based.
- [MacTeX](https://tug.org/mactex/) for macOS.
- [ShareLaTeX](https://www.sharelatex.com/) — edytor online.
- [Overleaf](https://www.overleaf.com/) — edytor online.
- [StackEdit](https://stackedit.io/) — In-browser markdown editor.

#### Edytory

- [TeXMaker](http://www.xm1math.net/texmaker/) Cross platform LaTeX editor.
- [TeXStudio](http://www.texstudio.org/) An enhanced fork of TeXMaker with more features.
- TeXShop and TeXworks (minimal editors)

#### Kompilatory

- Większość edytorów pozwoli Ci na wybór domyślnego kompilatora:

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY!!

:tada: Dziękuję Ci za ukończenie tego poradnika. To wszystko czego potrzebujesz do rozpoczęcia swojej przygody z LaTeX. :hammer:  
Jeśli będziesz potrzebował pomocy, [tutaj](http://www.latex-project.org/help/documentation/) znajdziesz wiele przydatnych informacji .

## Licencja

[![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION: You just DO WHAT THE FUCK YOU WANT TO.

<div id='donation'/>

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

A beer in your country can buy a meal in mine.

## Adnotacja od autora tłumaczenia

Autorem tłumaczenia jest Artur Komorowski (@aokomorowski). Jeśli widzisz w tekście błędy - proszę, popraw je. Jeśli uznasz, że LaTeX zmienił Twoje życie - podziękuj autorowi.
