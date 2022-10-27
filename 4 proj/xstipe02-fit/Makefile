#Author: Jiří Štípek

Filename=proj4
PACK=xstipe02-fit
INCLUDE=czechiso.bst


.PHONY: clean pack bibtex pdflatex

$(Filename).pdf: $(Filename).ps
	ps2pdf -sPAPERSIZE=a4 $^


$(Filename).ps: $(Filename).dvi
	dvips $^


$(Filename).dvi: $(Filename).tex
	latex $^
	make bibtex
	latex $^
	latex $^

bibtex: $(Filename).bib
	bibtex $(Filename)

pdflatex: $(Filename).tex
	pdflatex $^
	make bibtex
	pdflatex $^
	pdflatex $^

pack: $(PACK).tar.gz

$(PACK).tar.gz: $(Filename).tex $(Filename).bib $(INCLUDE)
	tar -czf $@ $^ Makefile

clean:
	rm -f $(Filename).aux $(Filename).dvi $(Filename).log $(Filename).ps $(Filename).synctex.gz $(Filename).fls $(Filename).fdb_latexmk $(Filename).bbl $(Filename).blg