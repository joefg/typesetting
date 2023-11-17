.PHONY: help clean

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

build: ## Build card
	lualatex card.tex

clean: ## Remove generated files
	rm card.log
	rm card.aux
	rm card.pdf
