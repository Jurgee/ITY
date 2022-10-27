#Author: Jiří Štípek

Filename=proj5
PACK=xstipe02-fit
IMAGE=./img


.PHONY: pdflatex pack clean

$(Filename).pdf: $(Filename).ps
	ps2pdf $^


$(Filename).ps: $(Filename).dvi
	dvips $^


$(Filename).dvi: $(Filename).tex
	latex $^
	latex $^


pdflatex: $(Filename).tex
	pdflatex $^
	pdflatex $^

pack: clean $(PACK).tar.gz

$(PACK).tar.gz: $(Filename).tex $(IMAGE)
	tar -czf $@ $^ Makefile

clean:
	rm -f $(Filename).aux $(Filename).dvi $(Filename).log $(Filename).ps\
	 $(Filename).synctex.gz $(Filename).fls $(Filename).fdb_latexmk $(Filename).nav\
	 $(Filename).out $(Filename).snm $(Filename).toc $(wildcard $(IMAGE)/*.pdf)