all: images stone-LDDTestingOverview.pptx stone-LDDTestingTechniques.pptx
images: generate_qrcodes.sh
	./generate_qrcodes.sh && touch images
stone-LDDTestingOverview.pptx: LDDTestingOverview.md images/common/*.png images/overview/*.png
	pandoc -o stone-LDDTestingOverview.pptx LDDTestingOverview.md
stone-LDDTestingTechniques.pptx: LDDTestingTechniques.md images/common/*.png images/techniques/*.png
	pandoc -o stone-LDDTestingTechniques.pptx LDDTestingTechniques.md
