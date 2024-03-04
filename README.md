# JHU Dissertation Template

This is an unofficial Johns Hopkins dissertation template with recent updates by Bibekananda Datta. As of February 2024, the template follows the dissertation formatting requirements provided by the [Johns Hopkins University Sheridan Library](https://www.library.jhu.edu/library-services/electronic-theses-dissertations/formatting-requirements/). 

Johns Hopkins Library is flexible in terms of the format except for the title page, margins, and overall double-spaced content. Be sure to check it before you proceed any further. It is the user's responsibility to ensure all the formatting requirements are met.


## History of the template

- The report-class-based template was created by R. Jacob Vogelstein in May 2007
- Updated by Noah J. Cowan on March 1, 2010
- Updated by Brian D. Weitzner on April 29, 2014 
- Updated by John Muschelli on January 29, 2016 
- Updated by Leonardo Collado Torres on April 13, 2016 
- Updated by John Clayton in December 2019
- The current version is updated by Bibekananda Datta on March 04, 2024



## What is included in the template

Since the template is based on the report class, it is subdivided into multiple chapters. For all the front matters (mandatory or optional), technical chapters, and back matters (references and appendices), there are separate .tex files. The `00-main.tex` file is the driver or root file which includes all the preamble, document settings, package settings, and macros as needed. I would recommend going through the different sections of this file to understand what are the options available. Compared to the previous version of the thesis template, the current version includes the following:

- Reorganization of the necessary packages (you may need more) and their settings.
- Modularized all the settings, formatting, and macros. You can add more as needed.
- Added specific settings for adding epigraphs before or after the chapter heading.
- Added settings to control the white space from the top of the chapter to the chapter heading.
- Added header option for each chapter. Will add a short header option for a larger chapter name.
- Updated the appearance of table of contents, list of figures, and list of tables.


## How to use the template

I prefer using Overleaf for all of my LaTeX compilation and I recommend it storngly. You can also to do locally. I am assuming at this stage you have a stable LaTeX system ready either locally on your computer or you're using an online platform and compile LaTeX scripts. Locally, you need to compile `00-main.tex` file using `pdflatex` which will call all the auxilary files to produce the PDF. For Overleaf, you can clone or download the repository and upload it as a .zip file to Overleaf by creating a New Project. It should compile without any error. There might be warnings, but you can ignore them. Go through the main file and other files to understand the structure of the template. Your bibliographic file has to be in BibLaTeX format. Use a citation manager to export it.


## Some useful comments and suggestions for using the template


- Some necessary variables to customize the formatting of the document are included at the beginning of the document. Understand what each variable does and change them as needed to customize the dissertation formatting there.
- Most common packages are added in the `LaTeX Package` sections. Add your package in there.
- Most of the common settings are available in the `Document Formatting` section in the main file. Additional settings related to the table of contents and epigraphs are separately available but a little bit more complicated.
- Add your math macros and settings in the `Math Settings and Macros` section. 
- The bibliography file is based on BibLaTeX which is a more modern package compared to BibTeX and natbib. Use Zotero (this is what I use) or some other citation manager to generate a standard BibLaTeX file.
- If your bib file name is different than the current file, then change it at the beginning of the document where all the variables are declared.
- Current `apa` (author-year format) and `nature` (numbered format) style options are there for the bibliography. Choose either of them or you can add something else depending on your field or department requirement or advisor's suggestion such as IEEE, MLA, Harvard, Chicago, etc. Find where the BibLaTeX package is added to the document and customize the options for the bibliographic package.
- Add all the figures in the `figures` subdirectory. You can add chapter-wise PDF files (which is what I prefer) or just add all of them as you have them.
- If you add a quote before the chapter heading, then you may want to increase the white spacing on top and all of your chapters will have some additional white space.
- For unnumbered chapters that you want to add to the table of contents, use the `\chap` command instead of the `\chapter*` command.
- Similarly, for unnumbered sections, subsections, and subsubsections that you would like to add to the table of contents, use `\sect`, `\subsect`, and `\subsubsect` commands.
- Tables are defined to have `\arraystretch{1.5}` (equivalent to double space). If you would like to customize it globally throughout the document, you can try decreasing/ increasing it. I suggest doing it locally by defining a group for each table (StackExhange or StackOverflow is your friend here) where you can redefine `\arraystretch` for the individual tables as needed.
- If the table is wider than the page, you may want to use the landscape tables which are placed sideways and may go over multiple pages (someone on StackExhange or StackOverflow has done it for sure).
- If the chapter name is too long, you may have to customize the header spacing in the geometry settings options to accommodate that. Alternatively, you can use it with a short header option. But if it gets difficult to customize, you may want to remove all the header options.
- Add more packages, customized macros, or maybe more chapters as needed. Happy Graduation!
