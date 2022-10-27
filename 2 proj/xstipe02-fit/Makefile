#Author: Jiří Štípek

Filename=proj2
PACK=xstipe02-fit


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


clean:
	rm -f $(Filename).aux $(Filename).dvi $(Filename).log $(Filename).ps\
	 $(Filename).synctex.gz $(Filename).fls $(Filename).fdb_latexmk $(Filename).nav\
	 $(Filename).out $(Filename).snm $(Filename).toc