print: article.pdf
	pdfjam -o 1.pdf --a4paper --landscape --fitpaper true --trim '0cm 23cm 0cm 0cm' article.pdf
	pdfjam -o 2.pdf --a4paper --landscape --fitpaper true --trim '0cm 0cm 0cm 23.5cm' article.pdf
	pdfjam -o printout.pdf --a4paper --landscape 1.pdf 2.pdf

clean:
	rm 1.pdf 2.pdf

.PHONY: print clean
