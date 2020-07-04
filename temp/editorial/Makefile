.PHONY: all clean

all: editorial.pdf

%.tex: %.ipynb
	jupyter nbconvert --to latex --template ieee.tplx $<

%.pdf: %.tex
	pdflatex $*
	bibtex $*
	pdflatex $*
	pdflatex $*
	rm -f $*.aux $*.out $*.log $*.bbl $*.blg


editorial.pdf: editorial.tex references.bib
editorial.tex: editorial.ipynb

clean:
	rm -f *.aux *.out *.log *.bbl *.blg
	rm -f editorial.pdf editorial.tex
	rm -rf paper_files
