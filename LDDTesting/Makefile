all: images stone-LDDTestingOverview.pptx stone-LDDTestingTechniques.pptx stone-LDDTestingOverview.pdf stone-LDDTestingTechniques.pdf
images: generate_qrcodes.sh
	./generate_qrcodes.sh && touch images
stone-LDDTestingOverview.pptx: LDDTestingOverview.md images/common/*.png images/overview/*.png
	pandoc -o stone-LDDTestingOverview.pptx LDDTestingOverview.md
stone-LDDTestingTechniques.pptx: LDDTestingTechniques.md images/common/*.png images/techniques/*.png
	pandoc -o stone-LDDTestingTechniques.pptx LDDTestingTechniques.md
stone-LDDTestingOverview.pdf: stone-LDDTestingOverview.pptx
	soffice --headless --convert-to pdf:"writer_pdf_Export:SelectPdfVersion=1" stone-LDDTestingOverview.pptx
stone-LDDTestingTechniques.pdf: stone-LDDTestingTechniques.pptx
	soffice --headless --convert-to pdf:"writer_pdf_Export:SelectPdfVersion=1" stone-LDDTestingTechniques.pptx