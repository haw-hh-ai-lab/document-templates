# This code is made availiable under the Creative Commons Attribution Share Alike
# License (cc-by-sa). You can find the full License text under
# [http://creativecommons.org/licenses/by-sa/3.0/]
#
# Copyright 2005 Dirk Jagdmann <doj@cubic.org>
# Copyright 2006-20013 Lutz Behnke <lutz.behnke@gmx.de>
#
#
# Formatiere das SWL-Handbuch zu html für die Webseite und PDF für den Ausdruck
#
# Benötigte Software: eine LaTeX Installation mit pdflatex und latex2html
#

# hier den Namen des Zentraldokumentes ohne Endung angeben.
MASTER=haw_style

doc:	pdf # html

pdf: $(MASTER).pdf

%.pdf: %.toc %.aux 
	pdflatex $*.tex

%.toc %.aux: %.tex
	pdflatex $<

%.tex: chapters/%.tex
	touch $@

clean:
	rm -f *.aux *.log *.toc *.out
