PDFS:=intro.pdf tesseroids.pdf fatiando.pdf moho.pdf conclusion.pdf

presentation.pdf: $(PDFS)
	pdfunite $^ $@

%.pdf: %.odp
	libreoffice --headless --convert-to pdf:impress_pdf_Export $<

clean:
	rm $(PDFS)
