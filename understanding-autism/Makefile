ODT_FILES=$(wildcard handbook-fr.odt)

%.pdf: %.odt
	soffice --convert-to pdf "$<"

all: $(ODT_FILES:.odt=.pdf)

.PHONY: all
