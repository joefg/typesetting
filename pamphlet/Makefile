.PHONY: help

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

all: clean pdf epub # Builds our files.

clean: ## Cleans generated files.
	rm -f typeset.pdf;
	rm -f typeset.epub;

pdf: ## Creates PDF
	pandoc text.md -o typeset.pdf;

epub: ## Creates EPUB
	pandoc text.md -o typeset.epub --metadata title="Lorem Ipsum";
