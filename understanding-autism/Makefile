ODT_FILES=$(wildcard handbook-fr.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"
	mv $@ raw.pdf
	gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dDownsampleColorImages=true -dColorImageResolution=300 -dNOPAUSE  -dBATCH -sOutputFile="$@" "raw.pdf"
	exiftool -Title="Comprendre l'autisme" $@
	exiftool -Author="AsIAm.ie / traduit par Bastien Confais" $@
	exiftool -Creator="v1.2019-07-01" $@
	exiftool -Producer= $@

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
