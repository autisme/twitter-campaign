guide.pdf:
	for dir in $(DIRS); do \
		inkscape --without-gui --export-pdf=$$dir/front.pdf $$dir/front.svg; \
		inkscape --without-gui --export-pdf=$$dir/back.pdf $$dir/back.svg; \
		pdfjam -o $$dir/flyer.pdf --paper a4paper --landscape $$dir/front.pdf $$dir/back.pdf; \
	done

clean:
	echo "not implemented"

all: guide.pdf


.PHONY: all clean guide.pdf
