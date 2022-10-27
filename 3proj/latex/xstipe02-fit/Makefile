#Author: Jiří Štípek

Filename=proj3
PACK=xstipe02-fit
PACKAGES=algorithm2e.sty


.PHONY: pdflatex pack clean

$(Filename).pdf: $(Filename).ps
	ps2pdf $^


$(Filename).ps: $(Filename).dvi
	dvips $^


$(Filename).dvi: $(Filename).tex
	latex $^
	latex $^

$(PACK).tar.gz: $(Filename).tex $(IMAGES_DIRECTORY) $(PACKAGES)
	tar -czf $@ $^ Makefile

pdflatex: $(Filename).tex
	pdflatex $^
	pdflatex $^


clean:
	rm -f $(Filename).aux $(Filename).dvi $(Filename).log $(Filename).ps\
	 $(Filename).synctex.gz $(Filename).fls $(Filename).fdb_latexmk $(Filename).nav\
	 $(Filename).out $(Filename).snm $(Filename).toc $(wildcard $(IMAGES_DIRECTORY)/*.pdf)