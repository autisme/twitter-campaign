printout_a4: p1.svg p2.svg p3.svg p4.svg
	inkscape --without-gui --export-pdf=p1.pdf p1.svg
	inkscape --without-gui --export-pdf=p2.pdf p2.svg
	inkscape --without-gui --export-pdf=p3.pdf p3.svg
	inkscape --without-gui --export-pdf=p4.pdf p4.svg

	pdfjam -o odd.pdf --trim '0cm 0cm 14.85cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;
	pdfjam -o even.pdf --trim '14.85cm 0cm 0cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;

	pdfjam odd.pdf 1 --outfile o1.pdf;
	pdfjam odd.pdf 2 --outfile o2.pdf;
	pdfjam odd.pdf 3 --outfile o3.pdf;
	pdfjam odd.pdf 4 --outfile o4.pdf;

	pdfjam even.pdf 1 --outfile e1.pdf;
	pdfjam even.pdf 2 --outfile e2.pdf;
	pdfjam even.pdf 3 --outfile e3.pdf;
	pdfjam even.pdf 4 --outfile e4.pdf;

	pdfjam o1.pdf e1.pdf --nup 2x1 --paper a4paper --landscape --outfile p1.pdf;
	pdfjam o2.pdf e4.pdf --nup 2x1 --paper a4paper --landscape --outfile p2.pdf;
	pdfjam o4.pdf e2.pdf --nup 2x1 --paper a4paper --landscape --outfile p3.pdf;
	pdfjam o3.pdf e3.pdf --nup 2x1 --paper a4paper --landscape --outfile p4.pdf;

	pdfjam -o printout_a4.pdf --paper a4paper --landscape p1.pdf p2.pdf p3.pdf p4.pdf

printout_a5: p1.svg p2.svg p3.svg p4.svg
	inkscape --without-gui --export-pdf=p1.pdf p1.svg
	inkscape --without-gui --export-pdf=p2.pdf p2.svg
	inkscape --without-gui --export-pdf=p3.pdf p3.svg
	inkscape --without-gui --export-pdf=p4.pdf p4.svg

	pdfjam -o odd.pdf --trim '0cm 0cm 14.85cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;
	pdfjam -o even.pdf --trim '14.85cm 0cm 0cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;

	pdfjam odd.pdf 1 --outfile o1.pdf;
	pdfjam odd.pdf 2 --outfile o2.pdf;
	pdfjam odd.pdf 3 --outfile o3.pdf;
	pdfjam odd.pdf 4 --outfile o4.pdf;

	pdfjam even.pdf 1 --outfile e1.pdf;
	pdfjam even.pdf 2 --outfile e2.pdf;
	pdfjam even.pdf 3 --outfile e3.pdf;
	pdfjam even.pdf 4 --outfile e4.pdf;

	pdfjam -o printout_a5.pdf --paper a5paper e1.pdf o2.pdf e2.pdf o3.pdf e3.pdf o4.pdf e4.pdf o1.pdf

display:
	inkscape --without-gui --export-pdf=p1.pdf p1.svg
	inkscape --without-gui --export-pdf=p2.pdf p2.svg
	inkscape --without-gui --export-pdf=p3.pdf p3.svg
	inkscape --without-gui --export-pdf=p4.pdf p4.svg
	pdfjam -o front.pdf --trim '14.85cm 0cm 0cm 0cm' p1.pdf
	pdfjam -o back.pdf --trim '0cm 0cm 14.85cm 0cm' p1.pdf
	pdfjam -o tmp.pdf --rotateoversize true --a5paper front.pdf p2.pdf p3.pdf p4.pdf back.pdf
	pdftk tmp.pdf  cat 1 2east 3east 4east 5 output display.pdf

all: display

clean:
	rm -f e1.pdf e2.pdf e3.pdf e4.pdf o1.pdf o2.pdf o3.pdf o4.pdf p1.pdf p2.pdf p3.pdf p4.pdf odd.pdf even.pdf
	rm -f front.pdf back.pdf tmp.pdf

.PHONY: printout_a4 printout_a5 display all clean
