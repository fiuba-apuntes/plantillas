HTLATEX = htlatex

# http://www.tug.org/applications/tex4ht/mn.html

all : htmlcompile.html

htmlcompile.html : htmlcompile.tex documento.tex set.png
	$(HTLATEX) htmlcompile.tex "matjax"

clean : 
	rm *.4??
	rm *.aux
	rm *.log
	rm *.dvi
	rm *.tmp
	rm *.lg
	rm *.idv
	rm *.xref
	