# OST Latex Beamer Theme

Diese Vorlage wurde für die Verwendung mit XeLatex entwickelt. Ein Beispiel findet sich unter [example](./example).

## Installation

Kopieren Sie den Inhalt des [theme](./theme) Ordners an einen geeigneten Ort im System. Unter macOS ist dies beispielsweise `~/Library/texmf/tex/latex`, unter Linux `~/texmf/tex/latex`. Bei Problemen könnte dieser [StackExchange Beitrag](https://tex.stackexchange.com/a/1138/12195) weiterhelfen.

## Anwendung

In [example](./example) können Sie mittels `xelatex ost-example.tex` die Beispielpräsentation erstellen.

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