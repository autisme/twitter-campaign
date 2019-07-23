ODT_FILES=$(wildcard resultat-gem.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"
	mv $@ raw.pdf
	gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dDownsampleColorImages=true -dColorImageResolution=300 -dNOPAUSE  -dBATCH -sOutputFile="$@" "raw.pdf"
	exiftool -Title="Les attentes d'un GEM autisme à Nantes" $@
	exiftool -Author="Chrystèle Potinière / Basien Confais" $@
	exiftool -Creator="v1.2019-07-01" $@
	exiftool -Producer= $@

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
