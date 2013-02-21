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
