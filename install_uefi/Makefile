tex_file=memo.tex
dvi_file=memo.dvi
pdf_file=memo.pdf


# *.dvi -> *.pdf
$(pdf_file) : $(dvi_file)
	dvipdfmx $<

# *.tex -> *.dvi
$(dvi_file) : $(tex_file)
	platex $< 

clean : 
	rm -rf ./$(pdf_file)

.PHONY : clean
