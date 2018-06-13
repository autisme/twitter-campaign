all: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o margin.pdf --paper a4paper --landscape cover_margin.pdf inside_margin.pdf

clean:
	rm -f cover_margin.pdf inside_margin.pdf

.PHONY: all
