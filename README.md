# OST Latex Beamer Theme

Diese Vorlage wurde für die Verwendung mit XeLatex entwickelt. Ein Beispiel findet sich unter [example-latex](./example-latex). Unter [example-markdown](./example-markdown) finden Sie ein Beispiel wie Sie Präsentationen in Markdown (via [Pandoc](https://pandoc.org/)) erstellen können.

## Installation

Kopieren Sie den Inhalt des [theme](./theme) Ordners an einen geeigneten Ort im System. Unter macOS ist dies beispielsweise `~/Library/texmf/tex/latex`, unter Linux `~/texmf/tex/latex`. Bei Problemen könnte dieser [StackExchange Beitrag](https://tex.stackexchange.com/a/1138/12195) weiterhelfen.

## Anwendung

In [example-latex](./example-latex) können Sie mit folgendem Befehl die Beispielpräsentation erstellen:

`xelatex ost-example.tex`

In [example-markdown](./example-markdown) können Sie die selbe Beispielpräsentation aus der Markdown-Datei [ost-example.md](./example-markdown/ost-example.md) mit folgendem Befehl erstellen ([Pandoc](https://pandoc.org/) erforderlich):

`pandoc -t beamer --pdf-engine=xelatex --template template.latex ost-example.md -s -o ost-example.pdf`

_Hinweis: Framesubtitle's sind via Markdown nicht unterstützt._

## Anpassungen

Es gibt verschiedene Möglichkeiten, das Theme anzupassen, allerdings muss dazu das (oben kopierte) Theme direkt editiert werden. Die definierten Fonts und Farben entsprechen dem Corporate Design und sollten nicht editiert werden. Allerdings könnte in [theme/beamerouterthemeost.sty](./theme/beamerouterthemeost.sty) angepasst werden, welche Informationen zur Präsentation im Footer erscheinen soll. Im Moment erscheint unten Links der Kurztitel der Präsentation, dies ist folgendermasse definiert:

```latex
\begin{textblock}{14.9}[0,0](\fpeval{2.24 + 0.3},17.93)
    \begin{beamercolorbox}[sep=0pt]{title in head/foot}
        \usebeamerfont{title in head/foot} \let\hyperlink\@secondoftwo\insertshorttitle\par%
    \end{beamercolorbox}%
\end{textblock}
```

Um hier beispielsweise den Autor anzuzeigen, genügt folgende Anpassung:

```latex
\begin{textblock}{14.9}[0,0](\fpeval{2.24 + 0.3},17.93)
    \begin{beamercolorbox}[sep=0pt]{title in head/foot}
        \usebeamerfont{title in head/foot} \insertauthor\par%
    \end{beamercolorbox}%
\end{textblock}
```

Feedback und Änderungsvorschläge nehmen wir sehr gerne entgegen, entweder per Issue oder noch besser direkt mit einem Pull Request.