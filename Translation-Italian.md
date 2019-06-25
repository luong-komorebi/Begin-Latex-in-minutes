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

* [Che cos'è LaTeX?](#che-cos'è-latex)
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
