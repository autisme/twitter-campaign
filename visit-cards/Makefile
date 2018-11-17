card.pdf: front.pdf back.pdf
	pdfjam  --outfile $@ --papersize '{8.5cm,5cm}' front.pdf back.pdf

template.pdf: front.pdf back.pdf
	pdflatex template.tex

front.pdf: front.svg
	inkscape --without-gui --export-pdf=$@ $<

back.pdf: back.svg
	inkscape --without-gui --export-pdf=$@ $<

blank.pdf: blank.svg
	inkscape --without-gui --export-pdf=$@ $<
