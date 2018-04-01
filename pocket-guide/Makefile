guide.pdf:
	for page in {1..4}; do \
		inkscape --without-gui --export-pdf=p$${page}.pdf p$${page}.svg; \
	done; \
	pdfjam -o guide.pdf --paper a4paper --landscape p1.pdf p2.pdf p3.pdf p4.pdf;

guide_inverted.pdf:
	for page in {1..4}; do \
		inkscape --without-gui --export-pdf=p$${page}.pdf p$${page}.svg; \
	done; \
	pdfjam -o odd.pdf --trim '0cm 0cm 14.85cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;
	pdfjam -o even.pdf --trim '14.85cm 0cm 0cm 0cm' p1.pdf p2.pdf p3.pdf p4.pdf;
	for page in {1..4}; do \
		pdfjam odd.pdf $${page} --outfile o$${page}.pdf; \
		pdfjam even.pdf $${page} --outfile e$${page}.pdf; \
	done; \
	pdf180 o2.pdf --outfile o21.pdf; mv o21.pdf o2.pdf; \
	pdf180 e4.pdf --outfile e41.pdf; mv e41.pdf e4.pdf; \
	pdf180 o3.pdf --outfile o31.pdf; mv o31.pdf o3.pdf; \
	pdf180 e3.pdf --outfile e31.pdf; mv e31.pdf e3.pdf; \
	pdfjam o1.pdf e1.pdf --nup 2x1 --paper a4paper --landscape --outfile p1.pdf; \
	pdfjam e4.pdf o2.pdf --nup 2x1 --paper a4paper --landscape --outfile p2.pdf; \
	pdfjam o4.pdf e2.pdf --nup 2x1 --paper a4paper --landscape --outfile p3.pdf; \
	pdfjam e3.pdf o3.pdf --nup 2x1 --paper a4paper --landscape --outfile p4.pdf; \
	pdfjam -o guide_inverted.pdf --paper a4paper --landscape p1.pdf p2.pdf p3.pdf p4.pdf;


clean:
	rm -f p1.pdf p2.pdf p3.pdf p4.pdf odd.pdf even.pdf e1.pdf e2.pdf e3.pdf e4.pdf o1.pdf o2.pdf o3.pdf o4.pdf

all: guide.pdf guide_inverted.pdf


.PHONY: all clean
