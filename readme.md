# Cloudnode User's Guide

Version 1.0<br />
http://docs.cloudno.de

## About

This guide is generated from the Cloudnode Wiki. Each chapter is a markdown file in this repository. The live version 
lives in the AppJet database and can be edited online through the Wiki admin pages. The PDF version is generated from time
to time from the same sources using Multimarkdown and LaTex. The resulting PDF can also be read on your Kindle or iPad.
   
## Building the PDF

The conversion is done in three steps:

1. Create the combined markdown file
   ../../Library/Application\ Support/MultiMarkdown/Utilities/mmd_merge.pl index.txt > guide.md

2. Generate the TeX file
   multimarkdown -t latex guide.md > guide.tex

3. Create PDF
   pdflatex guide.tex

## Download

[Cloudnode User's Guide](https://github.com/dvbportal/cloudnode-wiki/raw/master/guide.pdf)

## Required Tools to build the PDF (on Mac)

* **Multimarkdown:** https://github.com/fletcher/MultiMarkdown
* **LaTex Live 2011 Basic:** http://www.tug.org/mactex/2011/morepackages.html
* **peg-multimarkdown-latex-support:** https://github.com/fletcher/peg-multimarkdown-latex-support