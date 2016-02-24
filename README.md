# Praktischer Einstieg in LaTeX
Einfache Einführung in die Arbeit mit LaTeX

## Inhalt
Das Repository beinhaltet die LaTeX-Vorlage `protokoll.tex` zum Erstellen eines
Praktikumsprotokolls.  Zusätzlich liegen die benötigte Abbildung `plot.png`
sowie das BibTex-Literaturverzeichnis `literatur.bib` bei.

## Kompilieren
### LaTeX-Editoren
Der effizienteste Weg mit LaTeX-Dokumenten zu arbeiten ist der Einsatz eines
LaTeX-Editors wie beispielsweise [texmaker](http://www.xm1math.net/texmaker/) und
[Kile](http://kile.sourceforge.net/). Diese Verfügen nebennützlichen Funktionen
wieSyntax-Highlighting und Wortvervöllständigung meist auch eingebaute Lösungen
zur Erstellung des PDF-Dokumentes.

### Kommandozeile
Zum Kompilieren des PDF-Dokuments empiehlt es sich ein build-tool wie `latexmk`
zu nutzen. Das Skript trägt automatisch dafür Sorge, dass das Dokument häufig
genug kompiliert wird, um das Inhaltsverzeichnis, Referenzen und das
Literaturverzeichnis auf dem aktuellen Stand zu halten. `latexmk` lässt sich auf
der Kommandozeile wie folgt verwenden:

`$ ./latexmk -e "$pdflatex=q/pdflatex -interaction=nonstopmode/" -pdf protokoll.tex`

Diese doch sehr umständliche Eingabe lässt sich vereinfachen, wenn man `latexmk`
mit einem `alias` überlädt. In der Bash lässt sich dies mit folgendem Kommando
umsetzen:

`$ alias latexmk='latexmk -e "$pdflatex=q/pdflatex -interaction=nonstopmode/" -pdf'`

Dieser Befehl kann der `.bashrc` hinzugefügt werden, um ihn nicht bei jeder
neuen Shell-Session auszuführen zu müssen. Zusätzlich muss sich `latexmk` in
einem Verzeichnis befinden, das sich im Suchpfad (`PATH`) der aktuellen Shell
befindet. Sind beide Bedingungen erfüllt, vereinfacht sich der Aufruf zu:

`$ latexmk protokoll.tex`
