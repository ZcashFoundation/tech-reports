LATEX = pdflatex
BIBTEX = bibtex
MAIN = threat-model-network-privacy

all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).tex $(MAIN).bbl
	while $(LATEX) $(MAIN) && grep -q "Rerun to get" $(MAIN).log ; do true; done

$(MAIN).bbl: $(MAIN).bib
	$(LATEX) $(MAIN)
	$(BIBTEX) $(MAIN)

clean:
	rm -f *.bbl *.blg threat-model-network-privacy.pdf *.aux *.log *.out

