latexfile = ms
figures = figure1.pdf
biblio = refs

$(latexfile).pdf: $(latexfile).tex $(figures) formatting.tex
	pdflatex $(latexfile)
	bibtex $(latexfile)
	while (pdflatex $(latexfile) ; \
	grep -q "Rerun to get cross\|Rerun to get citations" $(latexfile).log ) do true ; \
	done
	rm -f $(latexfile).log $(latexfile).aux $(latexfile).bbl $(latexfile).blg $(latexfile).out formatting.aux

view:	$(latexfile).pdf
	open $(latexfile).pdf

clean:
	rm -f $(latexfile).log $(latexfile).aux $(latexfile).bbl $(latexfile).blg $(latexfile).out $(latexfile).pdf formatting.aux
