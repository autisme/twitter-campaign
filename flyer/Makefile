DIRS=$(wildcard */.)

$(DIRS):
	for dir in $(DIRS); do \
		inkscape --without-gui --export-pdf=$$dir/flyer_front.pdf $$dir/flyer_front.svg; \
		inkscape --without-gui --export-pdf=$$dir/flyer_back.pdf $$dir/flyer_back.svg; \
		pdfjam -o $$dir/flyer.pdf --paper a4paper --landscape $$dir/flyer_front.pdf $$dir/flyer_back.pdf; \
	done

clean:
	for dir in $(DIRS); do \
		rm $$dir/flyer_front.pdf $$dir/flyer_back.pdf; \
	done

all: $(DIRS)


.PHONY: all clean $(DIRS)
