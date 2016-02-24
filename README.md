# latex-simple
Einfache Einführung in die Arbeit mit LaTeX

Das Repository beinhaltet eine LaTeX-Vorlage zum Erstellen eines
Praktikumsprotokolls.  Zusätzlich liegen die benötigte Abbildung `plot.png`
sowie das BibTex-Literaturverzeichnis `literatur.bib` bei.

Zum Erstellen des PDF-Dokuments wird folgender Befehl in der Kommandozeile
abgesendet:

`$ ./latexmk -e "$pdflatex=q/pdflatex -interaction=nonstopmode/" -pdf protokoll.tex`

Diese doch sehr umständliche Eingabe lässt sich vereinfachen, wenn man `latexmk`
mit einem `alias` überlädt. In der Bash lässt sich dies mit dem Kommando
umsetzen:

`$ alias latexmk='latexmk -e "$pdflatex=q/pdflatex -interaction=nonstopmode/" -pdf'`

Dieser Befehl kann der `.bashrc` hinzugefügt werden, um ihn nicht bei jeder
neuen Shell-Session auszuführen. Zusätzlich muss sich `latexmk` in einem
Verzeichnis befinden, das sich im Suchpfad (`PATH`) der aktuellen Shell
befindet. Sind beide Bedingungen erfüllt, vereinfacht sich der Aufruf zu:

`$ latexmk protokoll.tex`
