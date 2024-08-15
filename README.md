[![Python application](https://github.com/wiso/ListOfPublicationsFromInspireHEP/actions/workflows/python-app.yml/badge.svg)](https://github.com/wiso/ListOfPublicationsFromInspireHEP/actions/workflows/python-app.yml)
# ListOfPublicationsFromInspireHEP

Create a list of publications from InspireHEP and produce a LaTeX document and a PDF. This tool can be useful when the list is very long and there are some LaTeX errors in the BibTeX entries.

## Install

In your (virtual)environment:

    python -m pip install -r requirements.txt

## How to use it

First create the BibTex file downloading all your bib entries, for the options try:

    ./create-bibtex -h

it downloads the entries from http://inspirehep.net/ and produces a BibTeX file as `bibtex_2016-02-07.bib`. If you get problems you can download the BibTex from inspire.hep, going on your profile and using the "cite all" button. Actually, this is faster, but you can download only 1000 entries. In this case, you can select a few years on the left and then merge the files.

Usually, many LaTeX errors are present, you can fix them with:

    ./check_biblio.py --fix-unicode <bibtexfilename.bib>

Finally to create the pdf:

    ./create_latex.py <bibtexfilename_new.bib>

SZ 15.08.2024

./create_bibtex.py --query find%20author%20o%20zenaiev

export EDITOR=nano

./check_biblio.py bibtex_2024-08-15.bib

./create_latex.py bibtex_2024-08-15_new.bib
