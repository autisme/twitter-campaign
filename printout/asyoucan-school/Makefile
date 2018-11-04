print_a4: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o print_a4.pdf --paper a4paper --landscape cover_margin.pdf inside_margin.pdf

print_a5: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o odd.pdf --trim '0cm 0cm 14.85cm 0cm' cover_margin.pdf inside_margin.pdf;
	pdfjam -o even.pdf --trim '14.85cm 0cm 0cm 0cm' cover_margin.pdf inside_margin.pdf;

	pdfjam odd.pdf 1 --outfile o1.pdf;
	pdfjam odd.pdf 2 --outfile o2.pdf;

	pdfjam even.pdf 1 --outfile e1.pdf;
	pdfjam even.pdf 2 --outfile e2.pdf;

	pdfjam -o print_a5.pdf --paper a5paper e1.pdf o2.pdf e2.pdf o1.pdf


display: inside_margin.svg cover_margin.svg
	inkscape --without-gui --export-pdf=cover_margin.pdf cover_margin.svg
	inkscape --without-gui --export-pdf=inside_margin.pdf inside_margin.svg
	pdfjam -o front.pdf --trim '14.85cm 0cm 0cm 0cm' cover_margin.pdf
	pdfjam -o back.pdf --trim '0cm 0cm 14.85cm 0cm' cover_margin.pdf
	pdfjam -o tmp.pdf --rotateoversize true --a5paper front.pdf inside_margin.pdf back.pdf
	pdftk tmp.pdf  cat 1 2east 3 output display.pdf

all: display

clean:
	rm -f o1.pdf o2.pdf e1.pdf e2.pdf odd.pdf even.pdf
	rm -f cover_margin.pdf inside_margin.pdf
	rm -f front.pdf back.pdf tmp.pdf

.PHONY: print_a4 print_a5 display all clean
