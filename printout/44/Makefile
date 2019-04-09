printout_a4: flyer.pdf
	inkscape --without-gui --export-pdf=flyer.pdf flyer.svg
	pdfjam -o front.pdf --trim '0cm 0cm 14.85cm 0cm' flyer.pdf
	pdfjam -o front1.pdf --trim '0cm 0cm 14.35cm 0cm' flyer.pdf
	pdfjam -o front2.pdf --paper a5paper --offset '0cm 0cm' front1.pdf
	pdfjam -o front3.pdf --paper a5paper --offset '0.5cm 0cm' front1.pdf
	pdfjam -o back.pdf --trim '14.85cm 0cm 0cm 0cm' flyer.pdf
	pdfjam front2.pdf front3.pdf --nup 2x1 --paper a4paper --landscape --outfile p1.pdf;
	pdfjam back.pdf back.pdf --nup 2x1 --paper a4paper --landscape --outfile p2.pdf;
	pdfjam -o printout_a4.pdf --paper a4paper --landscape p1.pdf p2.pdf

display: flyer.svg
	inkscape --without-gui --export-pdf=flyer.pdf flyer.svg
	pdfjam -o front.pdf --trim '0cm 0cm 14.85cm 0cm' flyer.pdf
	pdfjam -o back.pdf --trim '14.85cm 0cm 0cm 0cm' flyer.pdf
	pdfjam -o display.pdf --rotateoversize true --a5paper front.pdf back.pdf

all: display

clean:
	rm -f flyer.pdf front.pdf front1.pdf front2.pdf front3.pdf back.pdf p1.pdf p2.pdf

.PHONY: printout_a4 display all clean
