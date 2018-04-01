DIRS=$(wildcard */.)

$(DIRS):
	for dir in $(DIRS); do \
		inkscape --without-gui --export-pdf=$$dir/front.pdf $$dir/front.svg; \
		inkscape --without-gui --export-pdf=$$dir/back.pdf $$dir/back.svg; \
		pdfjam -o $$dir/flyer.pdf --paper a4paper --landscape $$dir/front.pdf $$dir/back.pdf; \
		pdf180 $$dir/back.pdf --outfile $$dir/back1.pdf; mv $$dir/back1.pdf $$dir/back.pdf; \
		pdfjam -o $$dir/flyer_inverted.pdf --paper a4paper --landscape $$dir/front.pdf $$dir/back.pdf; \
	done

clean:
	for dir in $(DIRS); do \
		rm $$dir/front.pdf $$dir/back.pdf; \
	done

all: $(DIRS)


.PHONY: all clean $(DIRS)
