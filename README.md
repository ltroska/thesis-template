About
=====

LaTeX template for Master, Bachelor, Diploma, and Student Theses with examples for algorithms, equations, figures, tables and bibliography.

More information at https://github.com/diehlpk/thesis-template

It originates from https://github.com/latextemplates/uni-stuttgart-computer-science-template

Characteristics
---------------
* UTF-8
* pdflatex
* latexmk
* Depends on biblatex

This template runs at Windows using the current [MiKTeX](http://www.miktex.org) distribution. Linux (TexLive full >= 2013 )should work without any issues. 

Using with your git repository
==============================

Initialization
--------------
This howto assumes that you have not a git repository for your thesis.
If you have, just add https://github.com/diehlpk/thesis-template.git as upstream and merge the branch "template" into your "master" branch.

1. Open command line
1. git clone https://github.com/diehlpk/thesis-template.git
1. cd thesis-template
1. git remote rename origin github
1. git checkout -b master

Now, you are on the master branch, where you can write your thesis and push it to your (remote) origin repository, in case you have one.

Merging updates from the template
---------------------------------
If you want to merge updates from github, do the following:

1. git fetch github
1. git merge github/template

LaTeX compilation
=================
The template is compiled using normal LaTeX commands.

If you want to include .svg graphics, inkscape has to be in your path.

Usual LaTeX run (latemk)
---------------

    latexmk -pdf ausarbeitung.tex

### latexmk configuration
This repository ships a `.latexmk` which is read by latexmk.
It is configured for Windows and especially sets Sumatra PDF as default PDF viewer.
You can make this local configuration a global configuration, when you put it at [the right place](http://tex.stackexchange.com/a/41149/9075).

If you want to add more packages, configure it there.
For instance, for support of makeglossaries see http://tex.stackexchange.com/questions/1226/how-to-make-latexmk-use-makeglossaries.


Automatic compilation using make
--------------------------------

    make

Make targets
============

* pdf (default) - Generates ausarbeitung.pdf
* aspell - Checks all files using aspell.
* clean - Removes all temporary files.
* mrproper - Cleans up and removes also editor backup files.
* stand - Creates a new PDF with the current status of the thesis.
* view - Opens the configured viewer

Alternatives
------------

* http://code.google.com/p/latex-makefile/
* https://github.com/ransford/pdflatex-makefile
* https://github.com/brotchie/latex-rubber-makefile
* See http://stackoverflow.com/questions/1240037/recommended-build-system-for-latex
* Current favorite: [LaTeX-Mk](http://latex-mk.sourceforge.net/).

Tweaks
======

Switching to English
--------------------

The template has been built primarily for German documents. English documents, however, are also very welcome.

Two steps to switch to English typesetting:

1. `ausarbeitung.tex`: Right on top: remove the `%` before `pointlessnumbers` (line 17)
1. `ausarbeitung.tex`: Exchange commands `\ifdeutsch` and `\ifenglisch`. (Lines 23,23 <-> 27,28).
1. Cleanup everything (e.g., `make clean`). Otherwise pdflatex will complain because of `ngerman`.

Change Appearance of Chapter Headings
-------------------------------------

Edit `preambel/chapterheads.tex`.

Add the title page of the mathematics department of the university of Bonn
--------------------------------------------------------------------------

1. Run make fetchtitlebonn
2. Uncomment %\input{titlePageBonn}
3. Comment \input{titlePage}

Final version
-------------

  - If you included some version control statements, please remove them. Currently, the template does not support any, but it used to support SVN.
  - By using `\largeparge` and `\shortpage`, single lines at the bottom or at the top of the page can be manually fixed.
  - Search the PDF for "TODO" or similar things. Remove `\usepackage{todonotes}` in `preambel/packages_and_options`.
  - Ensure that you run `pdflatex` at least three times and that there no "undefined references".
  - The margins are intended for a duplex printing. **Do not change them** (or do exactly know what you are doing).

Further Reading
---------------

See http://wiki.flupp.de/LaTeX


# Contained Files and Directories

## Main directory

### ausarbeitung.tex
* Main file
* New chapters are added by using `\input`
* Adjust title etc. here


### Makefile

The Makefile.

### README.md

This file.

## Bibliography

### bibliography/literatur.bib

Bibliography. BibTex format. Manage it with [JabRef](http://jabref.sf.net) or similar BibTeX tooling.

## content/

Place for the actual content

### content/einleitung.tex

First chapter: The introduction

### content/kapitel2.tex

Second chapter

### content/zusammenfassung`_`und`_`ausblick.tex

Conclusion and outlook.

### content/anhang.tex

Appendix

## graphics/

Directory containing the figures.

By using PDFLaTeX it is possible to use PDFs, JPGs, PNGs, ... We recommend to use PDFs to enable smooth scaling.

## macros/ 

Directory for macros.

### macros/commands.tex

Sample macros

## preambel/

Latex header of the document ("preambel" in latex)

### preambel/chapterheads.tex

Definition for the chapter headings.

### preambel/fonts.tex

Font selection

### preambel/margins.tex

Margin settings

Einstellung der Seitenr�nder

### preambel/packages`_`and`_`options.tex

Includes required packages and their options.

### preambel/pagestyle.tex

Defines the head and the foot of a page.
