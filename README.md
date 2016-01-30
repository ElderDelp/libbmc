libBMC
======

## Presentation

A generic Python library to manage bibliography and play with scientific
papers.


_Note_: This library is written for Python 3 and may not work with Python 2.
This is not a major priority for me, but if anyone needed to make it work with
Python 2 and want to make a PR, I will happily merge it :)


## Dependencies

Python dependencies are listed in the `requirements.txt` file at the root of
this repo, and can be installed with `pip install -r requirements.txt`.


External dependencies are [OpenDeTeX](https://code.google.com/p/opendetex/)
(an improved version of DeTeX) and the `pdftotext` and `djvutxt` programs.


OpenDeTeX is available as a Git submodule in the `libbmc/external` folder. If
you do not have it installed system-wide, you can use the following steps to
build it in this repo and the library will use it:

* `git submodule init; git submodule update` to initialize the Git submodules.
* `cd libbmc/external/opendetex; make` to build OpenDeTeX (see `INSTALL` file
  in the same folder for more info, you will need `make`, `gcc` and `flex` to
  build it).

OpenDeTeX is used to get references from a `.bbl` file (or directly from arXiv
as it uses the same pipeline).


`pdftotext` and `djvutxt` should be available in the packages of your
distribution and should be installed systemwide. Both are used to extract
identifiers from papers PDF files.


If you plan on using the `libbmc.citations.pdf` functions, you should also
install the matching software (`CERMINE`, `Grobid` or `pdf-extract`). See the
docstrings of those functions for more infos on this particular point.


## License

This code is licensed under an MIT license.


## Acknowledgements

Thanks a lot to the following authors and programs for helping in building
this lib:

* Dominika Tkaczyk, Pawel Szostek, Mateusz Fedoryszak, Piotr Jan Dendek and
Lukasz Bolikowski.
CERMINE: automatic extraction of structured metadata from scientific
literature.
In International Journal on Document Analysis and Recognition (IJDAR), 2015,
vol. 18, no. 4, pp. 317-335, doi: 10.1007/s10032-015-0249-8.
https://github.com/CeON/CERMINE

* https://github.com/CrossRef/pdfextract

* https://github.com/kermitt2/grobid

* https://github.com/sciunto-org/python-bibtexparser

* http://djvu.sourceforge.net/doc/man/djvutxt.html

* http://www.foolabs.com/xpdf/home.html

* https://code.google.com/p/opendetex/

* https://github.com/nathangrigg/arxiv2bib/

* https://github.com/xlcnd/isbnlib

* https://github.com/Anorov/PySocks

* http://docs.python-requests.org/en/latest/#
