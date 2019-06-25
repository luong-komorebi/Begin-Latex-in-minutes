[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
[Español](./Translation-Spanish.md) ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
Italiano 

---

# LaTeX in pochi minuti

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

**Riconoscimenti:** *Quanto scritto in questo documento deriva da mie esperienze universitarie e letture di diverso materiale sull'argomento. Non sono un professionista o un esperto ma un semplice studente con una passione per l'argomento. Chiunque può aprire una discussione nella sezione "Problemi" o aprire una Pull Request nel caso ritenga che qualcosa debba essere aggiunto o modificato. Se il mio lavoro vi è tornato utile una [donazione](#donation) è molto apprezzata.*

### Sommario

* [Che cos'è LaTeX?](#che-cosè-latex)
* [Perchè usare LaTeX?](#perchè-usare-latex)
* [Installare LaTeX](#installare-latex)
* [Il primo documento LaTeX](#il-primo-documento-latex)
* [Uno sguardo approfondito](#uno-sguardo-approfondito)
* [Supporto multilingue in LaTeX](#supporto-multilingue-latex)
* [Liste](#liste)
* [Paragrafi e sezioni](#paragrafi-e-sezioni)
* [Generare un sommario](#generare-un-sommario)
* [Note](#note )
* [Cosa sono i pacchetti?](#cosa-sono-i-pacchetti)
* [Tabelle](#tabelle)
* [Aggiungere immagini](#aggiungere-immagini)
* [Inserire porzioni di codice in LaTeX](#inserire-porzioni-di-codice-in-latex)
* [Più file in LaTeX](#piu-file-in-LaTeX)
* [Strumenti Aggiuntivi](#strumenti-aggiuntivi)

## Che cos'è LaTeX?

LaTeX, la cui pronuncia corretta è «La-tek», è un sistema per comporre documenti di altà qualità. È spesso impiegato in documenti medio-grandi di carattere tecnico-scientifico ma è utilizzabile per qualunque tipo di pubblicazione.

## Perchè usare LaTeX?

* LaTeX è gratis e multipiattaforma.
* Un file LaTeX è un semplice documento di testo modificabile con un qualsiasi editor di testo per poi essere facilmente covertibileconvertito in PDF.
* LaTeX separa il contenuto dallo stile del documento. Formatta lo stile, poi concentrati sul contenuto.
* Esperienza di lavoro più fluida rispetto a MS Word.
* Largo impiego nell'ambito scientifico.
* LaTeX rappresenta l'opzione migliore se si vogliono rappresentare formule matematiche più o meno complesse.

> LaTeX non è esente da svantaggi ma, viste i grandi vantaggi che il suo uso permette di ottenere, saperci lavorare è comunque utile.

## Installare LaTeX

Avrai bisogno di:

1. *Distribuzione LaTeX*
Personalmente uso [MiKTeX](https://miktex.org/about) per Windows.
2. *LaTeX Editor.*
Io utilizzo [TeXMaker](http://www.xm1math.net/texmaker/) per la facilità di editing, ricorda che in realtà un qualunque editor di testo può creare o modificare un file LaTeX.
3. *Visualizzatore di PDF* (opzionale)
Va bene di qualunque tipo, servirà a vedere il risultato del tuo lavoro.

È inoltre necessario scegliere un [compilatore](#strumenti-aggiuntivi). Il compilatore di default per la maggior parte degli editor è pdfLaTeX, nel caso sia necessario il support per caratteri TTF/OTF o Unicode utilizzare invece LuaLaTeX.

Un alternativa è l'uso di soluzioni online come [ShareLaTeX](https://www.sharelatex.com/).
Consultare la sezione [Strumenti aggiuntivi](#strumenti-aggiuntivi) per una grande varietà di alternative.

## Il primo documento LaTeX

Iniziamo con il più tradizionale degli **Hello World** in **LaTeX**.
Se hai installato **TexMaker** per prima cosa crea un nuovo file con estensione `.tex`. Inserisci quindi il codice qui sotto riportato, clicca poi su "quick build" per ottenere il tuo "Hello World!". Nel caso tu stia utilizzando un differente editor la procedura dovrebbe essere piuttosto simile.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % This is your content

\end{document}
```

Il risultato dovrebbe apparire così in TexMaker:
![](http://i.imgur.com/ZuD5N6U.png)

## Uno sguardo approfondito

:eyes: Guardando più da vicino il file LaTeX appena creato puoi notare:

* La prima linea di codice che comunica al programma che il documento su cui stiamo lavorando è di tipo **articolo** su foglio A4. È possibile utilizzare altri tipi di documenti come ad esempio **report** e **book**.
* La definizione del documento tra le due linee di codice **\begin{document}** e **\end{document}**. Questo è il "cuore" del documento, come il `main()` in *java* o *C++*... Senza di questo il documento non può essere convertito in PDF.
* La spazio tra begin ed end (nel nostro caso contenente soltanto `Hello World`) dove è presente il contenuto del documento da noi inserito.
* Un **segno percentuale** (%) denota un commento che LaTeX ignorerà non riportandolo nel documento in PDF finale.

#### :zap: Attenzione :zap:

* Soffermiamoci ancora sulle porzioni di codice **\begin{document}**, **\end{document}**, **\documentclass[a4paper]{article}**. Puoi notare come ci sia una sorta di pattern: in essi si possono riconoscere i **Comandi di Typesetting** (introdotti dal simbolo "\\") e i loro **Argomenti** (posizionati tra parentesi graffe {}). Un documento LaTeX non è altro che un comune documento di testo arricchito da questi comandi.
* Seguendo questa guida non dovresti incontrare particolari problemi. Nel futuro però potresti imbatterti in qualche difficoltà, **niente panico**. Gli errori riportati da LaTeX sono tendenzialmente di facile interpretazione e scritti in un linguaggio comprensibile. Se non riesci a risolverli prova a copiare ed incollare il messaggio d'errore su Google!
* Alcuni caratteri sono **designati a comandi speciali in LaTeX. Potrebbe essere necessario utilizzare un backslash (\\) per poterli visualizzare.**

![](http://i.imgur.com/9d0bXHH.png)

## Supporto multilingue in LaTeX

**Per utilizzare TeX con alcuni linguaggi sono necessario alcuni passaggi**

#### :white_check_mark: Primo metodo :white_check_mark:

Dato che pdfLaTeX, il compilatore di default, è limitato all'uso di 256 caratteri ciò può comportare alcuni problemi nelle fasi di creazione del PDF. Il primo metodo per aggirare questa limitazione consiste nell'uso di ["pacchetti"](#cosa-sono-i-pacchetti) (affronteremo l'argomento più avanti):

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Nell'esempio fornito utilizziamo i pacchetti `usepackage[T5]{fontenc}` e `usepackage[utf8]{inputenc}`; questi forniscono al compilatore l'abilità di codificare i caratteri corretti in modo che questi possano essere visualizzati nel PDF. In TexMaker il codice precedente produce il seguente risultato: 

![](http://i.imgur.com/UQEewYi.png)

mentre questo è ciò che si otterrebbe non si usassero i pacchetti appena illustrati :package::

![](http://i.imgur.com/xvzrQX2.png)

:umbrella: Lavorando con cartteri Cinesi-Giapponesi-Koreani può essere difficoltoso. In questi casi può tornare utile l'uso dei pacchetti `usepackage{CJKutf8}` unito a `\begin{CJK}{UTF8}` e `\end{CJK}`. Ecco un esempio con il Giapponese :jp::

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

Facile come mangiarsi un bel :sushi::

![](http://i.imgur.com/vAN1WUi.png)

#### :white_check_mark: Secondo metodo :white_check_mark:

Un altro modo per affrontare il problema consiste nel cambiare il proprio compilatore in [LuaLaTeX](#strumenti-aggiuntivi) (o [XeLaTeX](#strumenti-aggiuntivi)). Utilizzando i pacchetti `fontspec` e `polyglossia` la codifica Unicode funzionerà senza la necessità di ulteriori azioni da parte nostra:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Il font di default (Latin Modern) non supporta tutti i caratteri. È possibile definire un font installato nel nostro computer decommentando la linea di codice contenete la stringa `\setmainfont` e inserendo come argomento tra parentesi graffe il font che si desidera utilizzare (in formato TTF o OTF).

## Liste

    wip 
