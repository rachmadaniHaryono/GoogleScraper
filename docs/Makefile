# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    		=
SPHINXBUILD   		= sphinx-build
SPHINXAUTOBUILD 	= sphinx-autobuild
SPHINXPROJ    		= GoogleScraper
SOURCEDIR     		= source
BUILDDIR      		= build
PYTEST 						= pytest
PYTESTOPTS 				=
PYTESTWATCH 			= pytest-watch
PYTESTWATCHOPTS 	=

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

docs-autobuild:
	@$(SPHINXAUTOBUILD) "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

test:
	@$(PYTEST) --black --verbose $(PYTESTOPTS) $(O) ..

test-watch:
	@$(PYTESTWATCH) --runner "$(PYTEST) --black --verbose $(PYTESTOPTS) $(O) .." ..

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
