#
# Formatiere das SWL-Handbuch zu html f�r die Webseite und PDF f�r den Ausdruck
#
# Ben�tigte Software: eine LaTeX Installation mit pdflatex und latex2html
#

# hier den Namen des Zentraldokumentes ohne Endung angeben.
MASTER=sample_doc

doc:	pdf # html

pdf: $(MASTER).pdf

$(MASTER).pdf: $(MASTER).toc $(MASTER).aux $(MASTER).bbl
	pdflatex $(MASTER).tex

$(MASTER).toc $(MASTER).aux: $(MASTER).tex chapters/*.tex
	pdflatex $(MASTER).tex
	pdflatex $(MASTER).tex

%.bbl: %.aux bibliography/references.bib
	bibtex $*
 
clean:
	rm -f *.aux *.log *.toc *.out *.bbl *.blg
