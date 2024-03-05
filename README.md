# JHU Dissertation Template

This is an unofficial Johns Hopkins dissertation template with recent updates by Bibekananda Datta. As of February 2024, the template follows the dissertation formatting requirements provided by the [Johns Hopkins University Sheridan Library](https://www.library.jhu.edu/library-services/electronic-theses-dissertations/formatting-requirements/). Johns Hopkins Library is flexible in terms of the format except for the title page, margins, and overall double-spaced content. **However, be sure to check it before you proceed any further. It is the user's responsibility to ensure all the formatting requirements are met.**

This template is also [available on Overleaf as a template](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp).



## Version history for the template

- The report-class-based template was first created by R. Jacob Vogelstein in May 2007
- Updated by Noah J. Cowan on March 01, 2010
- Updated by Brian D. Weitzner on April 29, 2014 
- Updated by John Muschelli on January 29, 2016 
- Updated by Leonardo Collado Torres on April 13, 2016 
- Updated by John Clayton in December 2019
- The current version is updated by Bibekananda Datta on March 04, 2024


Compared to the previous version of the thesis template, the current version includes the following customizations:

  - Reduced the font size for chapter # and chapter title and white space throughout the document.
  - Reorganization of the necessary packages (you may need more) and their settings.
  - Modularized all the settings, formatting, and macros. You can add more as needed.
  - Added specific settings for adding quotes (epigraph) in each chapter. 
  - Added sentence-case header option with underline for each chapter.
  - Updated the appearance of table of contents, list of figures, and list of tables.



## What is included in this version of the template

Since the template is based on the report class, it is subdivided into multiple chapters. There are separate .tex files for all the front matters (mandatory or optional), technical chapters, and back matters (references and appendices).

- `00-main.tex` file is the driver or root file which includes all the preamble, document settings, package settings, and macros as needed as well as the auxiliary .tex files for each chapter. I would recommend going through the different sections of this file before you start working on to understand the available packages and options. 
- `figures` subdirectory contains all the figures for the thesis. You can add the figures as chapter-wise PDF files or as just individual images with allowable extensions.
- `thesis.bib` file is a biblatex file which contains all the bibliographic items. Use Zotero or some other citation manager to generate biblatex file.
- `latexmkrc` additional settings for the make file to generate PDF/A output. This is required to have in the main directory of Overleaf project.
- `output.xmpdata` contains simple meta-data to be be tagged in the final PDF/A file. This file is optional.



## How to use the template on Overleaf

I prefer using Overleaf for all of my LaTeX compilation and I recommend it storngly since Johns Hopkins provides premium account to all students for Overleaf. Premium Overleaf does fast compilation, allows sharing the project with multiple people (advisor, committee members, collaborator, labmates, friends, or family), keep track history which is great. You can recover file if you break it (hopefully you won't). Follow one of the three approaches to get started with this project on Overleaf. Then go through the main file and other files to see how the template is structured.

- To use it directly on Overleaf, [open the template here](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp). Then click on **Open as Template** and proceed from there to go through the template and edit it.

- If the overleaf version is outdated for some reason (Overleaf takes a bit of time to update the templates), then you can download / clone this repository from GitHub, then compress it as a zip file. Go to Overleaf, Click on **New Project** -> **Upload Project**, then upload the zipped folder. Continue...
  
- If you have your Overleaf and GitHub account linked and want to have copies of the project in both places, you can **fork** this repository. Then go to Overleaf, Click on **New Project** -> **Import from GitHub**, it should list the forked project for listing. Once imported, you can start working... But Overleaf and GitHub will not sync automatically; you will have to do it.

Once you have imported the project, you need to compile `00-main.tex` file using `pdflatex` option (default on Overleaf) which will call all the auxilary files included to produce the final PDF. It should compile without any error on Overleaf. There might be warnings, but you can ignore them. 



## Generating PDF/A compliant output file

Johns Hopkins Library requires the electronic copy of the thesis should be [generated in PDF/A format](https://www.adobe.com/uk/acrobat/resources/document-files/pdf-types/pdf-a.html) which is not trivial. Compiling LaTeX document is a bit of involved process but thanks to Overleaf that we do not really have to worry about it. [Check here to learn how do they do it](https://www.overleaf.com/learn/how-to/How_does_Overleaf_compile_my_project%3F). I have not done the compilation locally for this project and do not plan on doing it. So I am unable to provide any help in that regard.

- Learn about [latexmkrc file on Overleaf](https://www.overleaf.com/learn/latex/Articles/How_to_use_latexmkrc_with_Overleaf) which you will need to generate PDF/A file.
- [This documentation](https://www.overleaf.com/latex/templates/creating-pdf-slash-a-and-pdf-slash-x-files-with-the-pdfx-package/bbbycnbyqhnm) provides details on how to generate PDF/A compilant output on Overleaf. **Open as Template** to see what is included in the project.
  - Briefly, PDF/A compliant output is generating by including `\usepackage{pdfx}` command in the preamble, and to ensure the compilation worked properly, the project directory needs to include `latexmkrc` input file in which you will need to specify the timezone; [check supported timezones here](https://www.php.net/manual/en/timezones.php).
  - Optionally, to include the meta-data in the generated PDF, you can edit the `output.xmpdata`. The given fields are very simple.



## Some useful comments and suggestions for using the template

Overleaf has a huge collection of tutorials and examples on different LaTeX-related typesetting topics (margins and page size, table, footnote, bibliography management). You will most likely to find what you need there. But some specific suggestions for this template and projects are below:

- Most of the necessary variables to customize the formatting of the document are included at the beginning of the document. You can customize different spacing and style options using these variables. For most cases, tweaking these variables to your need and preference will be more than good enough to get desired format which conforms to library requirement. So, try to understand what each variable does by tweaking them before you start putting your contents in there, and finalize them as needed to customize the dissertation formatting there.

- In addition to these variables, if your bib file has a different name than the current file, then change the `BibFileName` varibale. Make sure to specify the correct name for the `graphicspath` as well.

- Add all the figures in the `figures` subdirectory. If your subdirectory name is different, then change `FigurePath` variable. You can add chapter-wise PDF files (which is what I prefer) or just add all of them as you have them in that directory.

- Most common and popular packages for writing dissertations are added in the `LaTeX Package` sections. Check the packages; add any additional package you need and/or customize your options there.

- The bibliography file is based on BibLaTeX which is a more modern package compared to BibTeX and natbib. Use Zotero (this is what I use) or some other citation manager to generate a standard BibLaTeX file.

- Currently `nature` (numbered format) and`apa` (author-year format) style options are there for the bibliography. Choose either of them or you can add something else depending on your discipline or department requirement or advisor's suggestion such as IEEE, MLA, Harvard, Chicago, etc. Find where the BibLaTeX package is added to the document and customize the options for the bibliographic package based on the style.

- By default, tables are defined to have `\arraystretch{1.5}` (equivalent to double space). If you would like to customize it globally throughout the document, you can try decreasing/ increasing the varible `GlobalTableSpacing`. I suggest doing it locally by defining a group for each table (StackExhange or StackOverflow is your friend here) where you can redefine `\arraystretch` for the individual tables as needed. Also if the table is wider than the page during editing, you may want to use the landscape tables which are placed sideways and may go over multiple pages (someone on StackExhange or StackOverflow has done it for sure).

- Most of the common settings are available in the `Document Formatting` section in the main file. Additional optional settings related to the table of contents, epigraphs, algorithms, and listing packages are separately available but a little bit more complicated. Unless you really want to customize a whole to your taste very spcifically, you can leave them as it is.

- You can also remove the settings for the optional packages that you do not indent to use such as epigraph, listings, algorithm2e, etc. But be careful while doing that; do not break the code.

- If you add a quote before the chapter heading, then you may want to increase the white spacing on top. In this case, all of the Chapters will have white space before Chapter # and title. I personally did not like it in the previous version of the template.

- For unnumbered chapters that you want to add to the table of contents, use the `\chap` command instead of the `\chapter*` command. (see, *Abstract* and *Acknowledgment*, for example). An exception to this is *Dedication* chapter because it does not have chapter title.

- Similarly, for unnumbered sections, subsections, and subsubsections that you would like to add to the table of contents, use `\sect`, `\subsect`, and `\subsubsect` commands, respectively. If you do not any of these environments to be added to the table of contents, then you can use standard * environments; such as `\section*{}`, etc.

- Add your math macros and settings in the `Math Settings and Macros` section. There's a section for non-math LaTeX macros as well.

- If you find all the packages and their settings and macros to be overwhelming and distracting during the editing process, you can cut and paste all these contents to a separate `settings.tex` file (name it as you like) in the project directory. Then you can use the command `input{settings.tex}` to make your main file appear cleaner and less distracting. `\input{}` command literally pastes content from the source file. See [managing large project on Overleaf](https://www.overleaf.com/learn/latex/Management_in_a_large_project).

- If the chapter name is too long, you may have to customize the header spacing in the geometry settings options to accommodate that. Alternatively, you can use it with a short header option. But if it gets difficult to customize, you may want to remove all the header options by commenting them out in the main file.

- Keep writing ... and Happy Graduation 🎉!


## Contributing to the project

This template was kept sufficiently general purpose for different disciplines with some customizations of special packages for demonstration purpose. If you have suggestion about specific LaTeX packages to your preference or discipline, it may not be a good idea to add them here. However, if you have suggestions about general formatting, you can fork the repostiroy and create a `pull request`, or simply just find me and let me know.
