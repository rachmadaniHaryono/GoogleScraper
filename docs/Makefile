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
PYTESTOPTS 				= --black --verbose --doctest-modules --doctest-glob="*.rst" --ignore="../Examples" --ignore="source/conf.py" ..
PYTESTWATCH 			= pytest-watch
PYTESTWATCHOPTS 	=
PYLINT 						= pylint
PYTLINTOPTS 			= --verbose --rcfile=../.pylintrc ../Tests ../GoogleScraper
PYLINTJSON2HTML 	= pylint-json2html

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

docs-autobuild:
	@$(SPHINXAUTOBUILD) "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: test
test:
	@$(PYTEST) $(PYTESTOPTS) && $(PYLINT) $(PYTLINTOPTS)

test-watch:
	@$(PYTESTWATCH) --runner "$(PYTEST) $(PYTESTOPTS)" ..

test-watch-pylint:
	@$(PYTESTWATCH) --runner "$(PYLINT) $(PYTLINTOPTS)" ..

test-pylint:
	@$(PYLINT) $(PYTLINTOPTS)

test-pylint-html:
	@$(PYLINT) $(PYTLINTOPTS) | $(PYLINTJSON2HTML) -o pylint.html

all: help

.PHONY: help Makefile all clean test

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
