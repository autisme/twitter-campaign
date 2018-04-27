DIRS=$(wildcard */.)

$(DIRS):
	for dir in $(DIRS); do \
		inkscape --without-gui --export-pdf=$$dir/cover.pdf $$dir/cover.svg; \
		inkscape --without-gui --export-pdf=$$dir/inside.pdf $$dir/inside.svg; \
		pdfjam -o $$dir/front.pdf --trim '14.85cm 0cm 0cm 0cm' $$dir/cover.pdf; \
		pdfjam -o $$dir/back.pdf --trim '0cm 0cm 14.85cm 0cm' $$dir/cover.pdf; \
		pdfjam -o $$dir/flyer.pdf --rotateoversize true --a5paper $$dir/front.pdf $$dir/inside.pdf $$dir/back.pdf; \
		pdftk $$dir/flyer.pdf  cat 1 2east 3 output $$dir/out.pdf; mv $$dir/out.pdf $$dir/flyer.pdf; \
		pdfjam -o $$dir/flyer_print.pdf --paper a4paper --landscape $$dir/cover.pdf $$dir/inside.pdf; \
		pdf180 $$dir/cover.pdf --outfile $$dir/cover1.pdf; mv $$dir/cover1.pdf $$dir/cover.pdf; \
		pdfjam -o $$dir/flyer_print_inverted.pdf --paper a4paper --landscape $$dir/cover.pdf $$dir/inside.pdf; \
	done

clean:
	for dir in $(DIRS); do \
		rm $$dir/front.pdf $$dir/back.pdf $$dir/cover.pdf $$dir/inside.pdf; \
	done

all: $(DIRS)


.PHONY: all clean $(DIRS)
