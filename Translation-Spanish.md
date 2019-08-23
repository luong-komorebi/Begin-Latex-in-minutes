[English](./readme.md) ·
[中文](./Translation-Chinese.md) ·
Español ·
[Português](./Translation-Portuguese.md) ·
[Français](./Translation-French.md) ·
[Русский](./Translation-Russian.md) ·
[Deutsch](./Translation-German.md) ·
[日本語](./Translation-Japanese.md) ·
[Polski](./Translation-Polish.md)

---

# Empieza con LaTeX en minutos

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

(Spanish translator's acknowledgement: I tried to translate this guide as the original meaning of the author as much as i could. If you think the translation is inappropriate, please feel free to modify it or add missing stuff you think would make this guide better. If you like this guide, please share to more people.)


**Aviso:** *Todo lo descrito abajo es desde mi experiencia en la universidad y después de leer varios materiales. No soy ni un profesional ni un experto, sino un estudiante que tiene gran pasión por el lenguaje. Cualquiera puede abrir una discusión en la sección de issues, o una solicitud de pull en caso de que algo deba ser modificado o agregado. Si valoras mi trabajo, una [donación](#donación) sería muy apreciada. ¡Gracias!*




### Table of Contents
* [¿Qué es LaTeX?](#qué-es-latex)
* [¿Por qué usar LaTeX?](#por-qué-usar-latex)
* [Configurar LaTeX](#configurar-latex)
* [Primer archivo LaTeX](#primer-arhivo-latex)
* [Un vistazo más profundo](#un-vistazo-más-profundo)
* [Uso multilenguaje](#uso-multilenguaje)
* [Listas](#listas)
* [Párrafos y secciones](#párrafos-y-secciones)
* [Haciendo una tabla de contenidos](#haciendo-una-tabla-de-contenidos)
* [Notas al pie](#notas-al-pie)
* [¿Qué es un paquete?](#qué-es-un-paquete)
* [Tablas](#tablas)
* [Añadiendo imágenes](#añadiendo-imágenes)
* [Insertar código en LaTeX](#insertar-código-en-latex)
* [Múltiples archivos en LaTeX](#múltiples-archivos-en-LaTeX)
* [Herramientas adicionales](#herramientas-adicionales)

## ¿Qué es LaTeX?

LaTeX, que es pronunciado «Lah-tech» o «Lay-tech» (para rimar con «blech»), es un sistema de preparación de documentos para tipografía de alta calidad. Es mayormente usado para documentos técnicos o científicos, mediano o grandes, pero puede ser usado para cualquier tipo de publicación.


## ¿Por qué usar LaTeX?

* LaTeX es gratis, multiplataforma.
* LaTeX es solo un documento de texto (el cual puede ser abierto por cualquier editor de texto) listo para convertirse a PDF.
* LaTeX separa contenido del estio. Diseña el estilo una vez, después concéntrate en el contenido.
* El flujo de trabajo es más rápido a comparación de MS Word.
* LaTeX es ampliamente usado para temas científicos.
* LaTeX es simlpemente la mejor opción cuando se trata de escribir expresiones matemáticas.

> LaTeX no viene sin inconvenientes, pero vale la pena totalmente aprenderlo.

## Configurar LaTeX

Necesitarás lo siguiente:


1. *Una distribución de LaTeX.*
Estouy usando [MiKTeX](https://miktex.org/about) para Windows.
2. *Un editor de LaTeX.*
Estoy usando [TeXMaker](http://www.xm1math.net/texmaker/) para facilitar la edición, sin embargo cualquier editor de texto puede modificar un archivo  LaTeX.
3. *Un visor de PDF.* (opcional)
Cualquier visor de PDF servirá. Esto es para que puedas ver el resultado.

Además, necesitas elegir un [compilador](#herramientas-adicionales). El compilador por defecto en la mayoría de editores es pdfLaTeX, pero si necesitas soporte (sin agragar más líneas de código) para Unicode o fuentes TTF/OTF desde tu sistema, usa XeLaTeX o LuaLatex.

O puedes elegir simplemente una solución online como [ShareLaTeX](https://www.sharelatex.com/).  

Por favor mira en [Herramientas adicionales](#herramientas-adicionales) para una amplia variedad de opciones.

## Primer archivo LaTeX

Hagamos el tradicional **Hello World** en **LaTeX**.
Si tienes **TexMaker** instalado, primero crea un nuevo archivo con la extensión `.tex`. después escribe el siguiente código para escribir "Hello world!" y presiona "Compilación rápida". Para otros editores de LaTeX, debería ser fácil seguir el mismo procedimiento.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % Este es tu contenido

\end{document}
```

Así es como debería verse en TexMaker:
![](http://i.imgur.com/ZuD5N6U.png)

## Un vistazo más profundo

:eyes: Un vistazo más profundo a tu primer archivo LaTeX muestra que:

* La primera línea le dice al *intérprete* que estás trabajando en un **artículo** de tamaño *A4*. Otros tipos de documentos con los que puedes estar trabajando son **reporte** (report), **libro** (book)..., etc.
* Un documento está rodeado por **\begin{document}** y **\end{document}** . Piensa en esto como el núcleo del documento, cómo el `main()` en *java* o *C++*..., sin él el documento no puede ser producido.
* La parte entre **\begin{document}** y **\end{document}** (que en este caso es `Hello World`) es simplemente tu propio contenido.
* Un **signo de porcentaje** (`$`) denota un comentario, que LaTeX ignorará.

#### :zap: Atención :zap:

* Fijándonos en **\begin{document}** , **\end{document}** , **\documentclass[a4paper]{article}** , podrás notar el patrón ahora. Estos son llamados **Comandos de tipografía**, que normalmente son precedidos por "`\`" y necesitan **argumentos** (colocados dentro de "`{}`"). LaTeX es normalmente texto, pero en esos argumentos radica su poder.
* Mientras estás siguiendo esta guía, todo deberá salir bien.Sin embargo, en el futuro encontrarás algunos problemas, **no entres en pánico**. Los reportes de error pueden ser leídos por humanos. Si no puedes resolverlos intuitivamente, una herramienta de búsqueda como Google será tu mejor amiga.
* Algunos caracteres están **predefinidos con significado especial en LaTeX. Deberás usar dobles diagonales ("`\\`") antes de ellos para una apropiada salida.**  

![](http://i.imgur.com/9d0bXHH.png)   

## Uso multilenguaje

**Algunos lenguajes o idiomas no funcionarán de inmediato (por ejemplo, el español y sus acentos, o la `ñ`). Para usar TeX con otros lenguajes tienes algunas opciones.**  

#### :white_check_mark: Primer método :white_check_mark:

El primer método es incluir ["paquetes"](#qué-es-un-paquete) (aprenderás esto después), por que pdfLaTeX está limitado a 256 caracteres y tiene algunos detalles de codificación. Por ejemplo:

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Aquí usamos los paquetes `usepackage[T5]{fontenc}` y `usepackage[utf8]{inputenc}` (`usepackage[T1]{fontenc}`) maneja los acentos del español correctamente. Esto es sencillo de entender; el paquete importará codificadores de fuentes para poder mostrar el contenido de una manera correcta. Si estás usando TexMaker así se verá el código anterior.

![](http://i.imgur.com/UQEewYi.png)

vs sin los paquetes (nota que los caracteres especiales se omiten) :package::  

![](http://i.imgur.com/xvzrQX2.png)  

:umbrella: Una situación complicada es manejar chino-japonés-coreano. Aquí, `usepackage{CJKutf8}` con `\begin{CJK}{UTF8}` y `\end{CJK}` son bastante úties. Aqui está la forma de escribir japonés :jp: :
```tex
\documentclass[a4paper]{article}
\usepackage{CJKutf8}

\begin{document}

\begin{CJK}{UTF8}{min}
この記事を読んでいただきありがとうございます。
%Thank you for reading this article. Gracias por leer esto
\end{CJK}

\end{document}
```

Tan fácil como comer :sushi: y :bento: :

![](http://i.imgur.com/vAN1WUi.png)  

#### :white_check_mark: Segundo método :white_check_mark:
Otro método es alcanzable si cambias tu compilador TeX de pdfLaTeX a [LuaLaTeX](#herramientas-adicionales) (or [XeLaTeX](#herramientas-adicionales)). Usando `fontspec` y `polyglossia`, Unicode funcionará de maravilla:

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```
La fuente por defecto (Latin Modern) no soporta todos los caracteres. Puedes, sin embargo, usar cualquier fuente que tengas instalada en tu sistema descomentando la línea `\setmainfont`. Las fuentes TTF y OTF están soportadas por completo.


## Listas

:straight_ruler: Es muy importnte que organices bien tu documento. Asi que, empezaremos por poner tus elementos en listas.
Dos tipos comunes de listas son **no ordered** y **ordenadas** list. Cada una puede ser manejada con facilidad en LaTeX:  
* Listas no ordenadas
Listas no ordenadas sólo necesitan **"itemize"**.
```tex
\begin{itemize}
\item Item. %un elemento
\item Another Item. %otro elemento
\end{itemize}
```  
* Listas ordenadas
Las listas ordenadas necesitan **"enumerate"**.
```tex
\begin{enumerate}
\item First Item. %primer elemento
\item Second Item.% segundo elemento
\end{enumerate}
```

Así es como los dos tipos de listas se ven en la salida:

![](http://i.imgur.com/jzN4RWm.png)

## Párrafos y secciones

:blue_book: Empezamos una sección con `\section` y un párrafo con `\paragraph` .
:orange_book: También puedes agregar subsecciones con `\subsection` y un subpárrafo con `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Haciendo una tabla de contenidos

:metal: Es útil para abrir secciones y subsecciones sin tener que desplazarse hasta ellas. El comando es  `\tableofcontents`

Ejemplo:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tips** : Puedes usar `\newpage` si quieres una nueva página.

## Notas al pie

Es extremadamente fácil usar footnote+label+ref para hacer todas las notas al pie que puedas imaginar.
Por ejemplo:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: ¿Lo ves?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tips** : Puedes usar `\newline` para crear un salto de línea.

## ¿Qué es un paquete?

LaTeX ofrece muchas funciones por defecto, sin embargo en algunas situaciones puede ser útil usar los llamados paquetes. Para importar un paquete en LaTeX, simplemente agrega `\usepackage{` :package:`}`


Aquí está un ejemplo de como usar dos paquetes para escribir expresiones matemáticas:

![](http://i.imgur.com/050nrfh.png)  

Más épico aún es como se muestran los circuitos:

![](http://i.imgur.com/If4lbLA.png)

:construction: Si necesitas algún paquete con requisitos específicos, lo mejor es hacer una búsqueda en Google. Por ejemplo, `amsmath` es ampliamente usado para escribir expresiones matemáticas, `circuitikz` es para diseño de circuitos, etc... Cubrirlos todos sería imposible para esta guía general.

## Tablas

Un ejemplo paráctico :thought_balloon: :

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

:star2: Esto es lo que muestra :star2: :

![](http://i.imgur.com/XbZJJ2E.png)

Veamos detenidamente :eyes: :

* Para las tablas , necesitamos un ambiente `\begin{table}` `código para el contenido de la tabla` `\end{table}` .
* Aprenderás sobre `h!` después, en la sección de imágenes. Va con `\centering` para mantener la tabla al centro de la página.
* `caption` es para describir, `label` es para agregar etiquetas. Verás más en la sección de imágenes.
* `tabular` es la parte más importante. Un ambiente de tabla siempre necesita un `tabular` dentro.
  - La parte `{l|c||r}` es donde formateamos el contenido dentro de la tabla. Podemos ver:
    * `l` o `c` o `r` significa que el contenido dentro de cada celda será alineado a la izquierda, al centro o a la derecha respectivamente.
    * `|` or `||` es el formato de las lineas (márgenes) verticales entre las columnas.
  - 1 & 2 & 3 => `1 2 3`  son los contenidos de cada celda. El ampersand `&` es usado para separar el contenido de cada celda en una fila.
  - Un `\hline` agrega una línea horizontal entre filas.

:bangbang: **Tips** Puedes usar un paquete :package: llamado booktabs `\usepackage{booktabs}` para crear tablas visualmente más atractivas.

## Añadiendo imágenes

Para añadir una imagen a un archivi LaTeX, necesitas usar un ambiente `figure` y el paquete `graphicx`.

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Tips**: Pon [width=\linewidth] para hacer (escalar) la imagen del tamaño del ancho del documento. Si quieres que la imagen sea flotante, necesitas agregar el atributo al principio de un cierto valor. Tambien `fig` es para poder hacer una referencia a esa imagen después.

```tex
\begin{figure}[h!]
```

:passport_control: Los valores aceptados son :

* h (here) - la misma ubicación
* t (top) - parte superior de la página
* b (bottom) - parte inferior de la página
* p (page) - en una ṕágina extra
* ! (override) - forzará una ubicación especificada

Así es como se ve la imagen :

![](http://i.imgur.com/ysY9MOb.png)

## Insertar código en LaTeX

#### :white_check_mark: Primer método :white_check_mark:

Un aspecto al compilar texto es que es de bastante importancia para programadores y desarroladores el qué tan profesionalmente se inserte código en un documento.  
Para LaTeX, el proceso es simple y muy profesional. Solo envolvemos el código en un comando predefinido y listo.

Ejemplo :

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello world!

\begin{verbatim} %código de C++
#include <iostream>

int main()
{
	std::cout << "hello world!\n";
	return 0;
}
\end{verbatim}

\end{document}
```

:speech_balloon: **LaTeX soporta la sintaxis de estos lenguajes** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

Como puedes ver, con **{verbatim}** puedes insertar fácilmente código sin preocuparte por cómo la sintaxis se verá. Así es como se ve sin hacer nada más, limpio y profesional:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Segundo método :white_check_mark: :white_check_mark:

Este método te da más opciones, incluyendo insertar código **inline**, hacer **estilos propios** de código, elegir un **lenguaje en específico**, **importar código** **desde** otro **archivo** en el mismo directorio.... Con este método no usas **verbatim**, sino que incluyes un paquete llamado `listings`.

Considera el siguiente ejemplo:
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
Aquí podemos observar:

1. Para insertar un bloque de código, empezamos con `\begin{lstlisting}` y terminamos con `\end{lstlisting}`
2. Para importar código desde otro archivo en el mismo directorio usamos `lstinputlisiting{name_of_file}`
3. Para especificar un lenguaje, usamos `[language=C++]`
4. Para insertar código inline, usamos `\lstinline`
5. Para aplicar estilos propiios, usamos `\usepackage{color}` y definimos nuestros propios estilos, después definimos el listing con nuestro tema (por favor revisa el código más abajo). Puedes modificar muchas cosas para crear tu propio estilo, pero necesitas leer la documentación para saber que propiedad modificar.
6. ¿Te interesa? Más [acá](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Así es como se ve el código en TexMaker:

![](http://i.imgur.com/XwwDJNo.png)

## Múltiples archivos en LaTeX

Cuando usamos LaTeX, podemos encontrar que un documento es demasiado grande, por cuestiones de practicidad. Entonces dividimos el archivo (para mejor orden) y de esta forma se más manejable.

Veamos el ejemplo.

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

Es un archivo LaTeX normal. Ahora, dividiremos el contenido en dos partes usando el comando `\input` keyword:


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

Ahora el archivo principal se ve diferente, pero mejor documentado y más legible. Aquí está el resultado en TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Tips** : Para legibilidad, claridad y mantenimiento, es muy recomendable que dividas tu `archivo principal` simstemáticamente, jerárquicamente y científicamente. No dividas sin razones o tendrás un lío después.

## Herramientas adicionales

#### Distribuciones

* [MiKTeX](https://miktex.org/about) para Windows.
* [TeX Live](https://www.tug.org/texlive/) para Linux y basadas en Unix.
* [MacTeX](https://tug.org/mactex/) para macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — un editor online.
* [Overleaf](https://www.overleaf.com/) — un editor online colaborativo.
* [StackEdit](https://stackedit.io/) - Editor de markdown en tu navegador.

#### LaTeX Editors

* [TeXMaker](http://www.xm1math.net/texmaker/) Editor LaTeX multiplataforma.
* [TeXStudio](http://www.texstudio.org/) Un fork de TexMaker supercargado con más características.
* TeXShop y TeXworks (editores mínimos)

#### LaTeX Compilers

* La mayoría de editores te darán la opción de cambiar el compialdor por defecto, aquí hay un ejemplo:

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY !!

:tada: ¡Gracias por completar la guía! Eso es básicamente todo lo que necesitas saber sobre LaTeX. :hammer:  
Si tienes interés por aprender, más sobre LaTeX se puede encontrar [acá](http://www.latex-project.org/help/documentation/) o en toda la web, dependiendo de lo que necesites.

## Licencia

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**LICENCIA PÚBLICA PARA QUE HAGA LO QUE LE DÉ LA GANA**  
Derechos de autor (C) 2016 Luong Vo  
Se permite la copia y distribución de forma literal o copias modificadas de este documento de licencia, y su modificación están permitidas siempre que el se cambie el nombre. (Changing it is allowed as long as the name is changed).  
TÉRMINOS Y CONDICIONES PARA LA COPIA, DISTRIBUCIÓN & MODIFICACIÓN: Eso sí, HAGA LO QUE LE DÉ LA GANA.


<div id='donación'/>  

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

Una cerveza en tu pais puede comprar una comida en el mío.
