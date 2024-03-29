.PHONY: help

help:
	@grep -E '^[a-zA-Z_0-9-]+:.*?## .*$$' $(MAKEFILE_LIST) \
		| sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

all: clean a5 a4 epub mobile ## Builds our files

clean: ## Cleans generated files
	rm -f typeset-*.pdf;
	rm -f typeset.epub;
	rm -f typeset.html;

a5: ## Creates a A5-sized PDF
	pandoc -V papersize:a5 text.md -o typeset-a5.pdf;

a4: ## Creates a A4-sized PDF
	pandoc -V papersize:a4 text.md -o typeset-a4.pdf;

html: ## Creates a singular HTML page
	pandoc \
		--template template.html \
		text.md -o typeset.html

mobile: ## Creates a mobile-sized PDF (80mm x 150mm) with a 5mm margin
	pandoc \
		-V geometry:papersize="{80mm,150mm}" \
		-V geometry:margin=5mm \
		-V font:11pt \
		text.md -o typeset-mobile.pdf;

epub: ## Creates an EPUB
	pandoc text.md -o typeset.epub;
