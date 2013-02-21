#
# Formatiere das SWL-Handbuch zu html für die Webseite und PDF für den Ausdruck
#
# Benötigte Software: eine LaTeX Installation mit pdflatex und latex2html
#

# hier den Namen des Zentraldokumentes ohne Endung angeben.
MASTER=sample_doc

doc:	pdf # html

pdf: $(MASTER).pdf

$(MASTER).pdf: $(MASTER).toc $(MASTER).aux $(MASTER).bbl
	pdflatex $(MASTER).tex

$(MASTER).toc $(MASTER).aux: $(MASTER).tex chapters/*.tex chapters/*.aux
	pdflatex $(MASTER).tex
	pdflatex $(MASTER).tex

%.bbl: %.aux chapters/*.aux bibliography/references.bib
	bibtex $*
 
clean:
	rm -f *.aux *.log *.toc *.out *.bbl *.blg
