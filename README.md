# JHU Dissertation Template

This is an unofficial Johns Hopkins dissertation template with recent updates by Bibekananda Datta. As of February 2024, the template follows the dissertation formatting requirements provided by the [Johns Hopkins University Sheridan Library](https://www.library.jhu.edu/library-services/electronic-theses-dissertations/formatting-requirements/). Johns Hopkins Library is flexible in terms of the format except for the title page, margins, and overall double-spaced content. **Be sure to check it before you proceed any further. It is the user's responsibility to ensure all the formatting requirements are met.**

This template is also [available on Overleaf as a template](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp).



## History of the template

- The report-class-based template was created by R. Jacob Vogelstein in May 2007
- Updated by Noah J. Cowan on March 1, 2010
- Updated by Brian D. Weitzner on April 29, 2014 
- Updated by John Muschelli on January 29, 2016 
- Updated by Leonardo Collado Torres on April 13, 2016 
- Updated by John Clayton in December 2019
- The current version is updated by Bibekananda Datta on March 04, 2024



## What is included in the template

Since the template is based on the report class, it is subdivided into multiple chapters. For all the front matters (mandatory or optional), technical chapters, and back matters (references and appendices), there are separate .tex files. The `00-main.tex` file is the driver or root file which includes all the preamble, document settings, package settings, and macros as needed. I would recommend going through the different sections of this file to understand what are the options available. Compared to the previous version of the thesis template, the current version includes the following customization:

- Reduced the font size for chapter # and chapter title and white space throughout the document.
- Reorganization of the necessary packages (you may need more) and their settings.
- Modularized all the settings, formatting, and macros. You can add more as needed.
- Added specific settings for adding quotes (epigraph) in each chapter. 
- Added sentence-case header option with underline for each chapter.
- Updated the appearance of table of contents, list of figures, and list of tables.



## How to use the template

I prefer using Overleaf for all of my LaTeX compilation and I recommend it storngly since Johns Hopkins provides premium account to all students for Overleaf. To use it directly on Overleaf, [open the template here](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp). Click on **Open as Template** and proceed from there to go through the template and edit it. If the overleaf version is outdated for some reason (Overleaf takes a bit of time to update the templates), then you can download / clone this repository from GitHub, then compress it as a zip file. Go to Overleaf, Click on New Project -> Upload Project, then upload the zipped folder.

You need to compile `00-main.tex` file using `pdflatex` option (that's default on Overleaf) which will call all the auxilary files included to produce the final PDF. It should compile without any error on Overleaf. There might be warnings, but you can ignore them. Go through the main file and other files to understand the structure of the template. Your bibliographic file has to be in BibLaTeX format. Use a citation manager (such as Zotero) to export it in that format.

**PS:** In case you prefer to do it locally, clone or download the repository. You need to have a LaTeX (text) editor and compiler. Unless you have not done it before, it maybe a bit challenging task to do for the first time. I have not done it for this project and unable to provide any comment on it. 


## Some useful comments and suggestions for using the template


- Some necessary variables to customize the formatting of the document are included at the beginning of the document. Understand what each variable does and change them as needed to customize the dissertation formatting there.
- Most common packages are added in the `LaTeX Package` sections. Add your package and options in there.
- Most of the common settings are available in the `Document Formatting` section in the main file. Additional optional settings related to the table of contents, epigraphs, algorithms, and listing packages are separately available but a little bit more complicated.
- Add your math macros and settings in the `Math Settings and Macros` section. 
- The bibliography file is based on BibLaTeX which is a more modern package compared to BibTeX and natbib. Use Zotero (this is what I use) or some other citation manager to generate a standard BibLaTeX file.
- If your bib file name is different than the current file, then change it at the beginning of the document where all the variables are declared.
- Currently `nature` (numbered format) and`apa` (author-year format) style options are there for the bibliography. Choose either of them or you can add something else depending on your discipline or department requirement or advisor's suggestion such as IEEE, MLA, Harvard, Chicago, etc. Find where the BibLaTeX package is added to the document and customize the options for the bibliographic package based on the style.
- Add all the figures in the `figures` subdirectory. You can add chapter-wise PDF files (which is what I prefer) or just add all of them as you have them.
- If you add a quote before the chapter heading, then you may want to increase the white spacing on top and all of your chapters will have some additional white space.
- For unnumbered chapters that you want to add to the table of contents, use the `\chap` command instead of the `\chapter*` command.
- Similarly, for unnumbered sections, subsections, and subsubsections that you would like to add to the table of contents, use `\sect`, `\subsect`, and `\subsubsect` commands.
- Tables are defined to have `\arraystretch{1.5}` (equivalent to double space). If you would like to customize it globally throughout the document, you can try decreasing/ increasing it. I suggest doing it locally by defining a group for each table (StackExhange or StackOverflow is your friend here) where you can redefine `\arraystretch` for the individual tables as needed.
- If the table is wider than the page, you may want to use the landscape tables which are placed sideways and may go over multiple pages (someone on StackExhange or StackOverflow has done it for sure).
- If the chapter name is too long, you may have to customize the header spacing in the geometry settings options to accommodate that. Alternatively, you can use it with a short header option. But if it gets difficult to customize, you may want to remove all the header options.
- Add more packages, customized macros, or maybe more chapters... Happy Graduation 🎉 !
