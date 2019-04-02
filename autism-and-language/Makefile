ODT_FILES=$(wildcard language.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"

%.png: %.pdf
	convert "$<"[0] -thumbnail 800x800 -bordercolor white -background black +polaroid "$@"

#all: $(ODT_FILES:.odt=.pdf) $(ODT_FILES:.odt=.png)

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
