poster_a4_v0.pdf: poster_v0.svg
	inkscape --without-gui --export-pdf=$@ $<

poster_a4_v1.pdf: poster_v1.svg
	inkscape --without-gui --export-pdf=$@ $<

poster_a4_v2.pdf: poster_v2.svg
	inkscape --without-gui --export-pdf=$@ $<

poster_a3_v0.pdf: poster_a4_v0.pdf
	pdfjam $< --paper a3paper --outfile $@

poster_a3_v1.pdf: poster_a4_v1.pdf
	pdfjam $< --paper a3paper --outfile $@

poster_a3_v2.pdf: poster_a4_v2.pdf
	pdfjam $< --paper a3paper --outfile $@

poster_a3_v0_split.pdf: poster_a3_v0.pdf
	pdfjam --outfile odd.pdf --paper a4paper --landscape --trim '0cm 21cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a4paper --landscape --trim '0cm 0cm 0cm 21cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a4paper --landscape odd.pdf even.pdf

poster_a3_v1_split.pdf: poster_a3_v1.pdf
	pdfjam --outfile odd.pdf --paper a4paper --landscape --trim '0cm 21cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a4paper --landscape --trim '0cm 0cm 0cm 21cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a4paper --landscape odd.pdf even.pdf

poster_a3_v2_split.pdf: poster_a3_v2.pdf
	pdfjam --outfile odd.pdf --paper a4paper --landscape --trim '0cm 21cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a4paper --landscape --trim '0cm 0cm 0cm 21cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a4paper --landscape odd.pdf even.pdf

poster_a2_v0.pdf: poster_a4_v0.pdf
	pdfjam $< --paper a2paper --outfile $@

poster_a2_v1.pdf: poster_a4_v1.pdf
	pdfjam $< --paper a2paper --outfile $@

poster_a2_v2.pdf: poster_a4_v2.pdf
	pdfjam $< --paper a2paper --outfile $@

poster_a2_v0_split.pdf: poster_a2_v0.pdf
	pdfjam --outfile odd.pdf --paper a3paper --landscape --trim '0cm 29.7cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a3paper --landscape --trim '0cm 0cm 0cm 29.7cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a3paper --landscape odd.pdf even.pdf

poster_a2_v1_split.pdf: poster_a2_v1.pdf
	pdfjam --outfile odd.pdf --paper a3paper --landscape --trim '0cm 29.7cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a3paper --landscape --trim '0cm 0cm 0cm 29.7cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a3paper --landscape odd.pdf even.pdf

poster_a2_v2_split.pdf: poster_a2_v2.pdf
	pdfjam --outfile odd.pdf --paper a3paper --landscape --trim '0cm 29.7cm 0cm 0cm' --outfile odd.pdf $<
	pdfjam --outfile even.pdf --paper a3paper --landscape --trim '0cm 0cm 0cm 29.7cm' --outfile even.pdf $<
	pdfjam  --outfile $@ --paper a3paper --landscape odd.pdf even.pdf
