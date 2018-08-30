print: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o printout.pdf --paper a4paper --landscape cover_margin.pdf inside_margin.pdf

display: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o front.pdf --trim '14.85cm 0cm 0cm 0cm' cover_margin.pdf
	pdfjam -o back.pdf --trim '0cm 0cm 14.85cm 0cm' cover_margin.pdf
	pdfjam -o tmp.pdf --rotateoversize true --a5paper front.pdf inside_margin.pdf back.pdf
	pdftk tmp.pdf  cat 1 2east 3 output display.pdf

all: print

clean:
	rm -f cover_margin.pdf inside_margin.pdf
	rm -f front.pdf back.pdf tmp.pdf

.PHONY: print display all clean
