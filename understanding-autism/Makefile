ODT_FILES=$(wildcard handbook-fr.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"
	mv $< raw.pdf
	gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dDownsampleColorImages=true -dColorImageResolution=300 -dNOPAUSE  -dBATCH -sOutputFile="$<" "raw.pdf"

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
