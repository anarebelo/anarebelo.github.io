
all:
	sed -r '/^Address/d' authenticus_export.bib > literature_without_addr.bib
	sed -r '/^Abstract/d' literature_without_addr.bib > literature_without_abs.bib

	sed -r 's/\{\{/\{/g' literature_without_abs.bib > literature_without_brack.bib
	sed -r 's/\}\}/\}/g' literature_without_brack.bib > literature.bib
	bibtex2html -o literature -nodoc -q literature.bib
	mv -v literature.html ../themes/hugo-coder/layouts/partials/components/
	mv -v literature_bib.html ../content/publications/

	# pandoc-citeproc -y literature.bib > literature.yml
