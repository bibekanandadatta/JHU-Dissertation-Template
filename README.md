# JHU Dissertation Template

This is an unofficial thesis (masters) or dissertation (PhD) template for Johns Hopkins with recent updates by Bibekananda Datta. As of March 2024, the template follows the dissertation formatting requirements provided by the [Johns Hopkins University Sheridan Library](https://www.library.jhu.edu/library-services/electronic-theses-dissertations/formatting-requirements/). Johns Hopkins Library is flexible in terms of the format except for the title page, margins, and overall double-spaced content. **However, be sure to check the requirements before you proceed any further. It is the user's responsibility to ensure all the formatting requirements are met.**

This template is also [available on Overleaf as an unofficial template](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp). However, GitHub is likely to be the most updated one. Details of using this repository on Overleaf can be found below.



## Version history for the template

- The report-class-based template was first created by R. Jacob Vogelstein in May 2007
- Updated by Noah J. Cowan on March 01, 2010
- Updated by Brian D. Weitzner on April 29, 2014 
- Updated by John Muschelli on January 29, 2016 
- Updated by Leonardo Collado Torres on April 13, 2016 
- Updated by John Clayton in December 2019
- The current version is updated by Bibekananda Datta on March 04, 2024


Previous version of the template used default options for LaTeX report class and different packages which had unusually large font size and extra white spaces around different environment. So, I decided to reorganize the template and add more customization by loading necessary packages. Compared to the previous version, for the current version of the template, I have:

  - Added cutomization options to control the font size and shape of different headings.
  - Added customization options to control the white space for different environments.
  - Reorganized the loading of common packages (you may need more) and their settings.
  - Modularized all the settings, formatting, and macros. You can add more as needed.
  - Added specific settings for adding quotes (epigraph), algorithm, and codes, in each chapter.
  - Added examples of cutomized macros for mathematical and non-mathematical environments.
  - Updated the appearance of table of contents, list of figures, and list of tables.



## What is included in this version of the template

Since the template is based on the report class, it is subdivided into multiple chapters. There are separate .tex files for all the front matters (mandatory or optional), technical chapters, and back matters (references and appendices).

- `00-main.tex` file is the driver or root file which includes all the preamble, document settings, package settings, and macros as needed as well as the auxiliary .tex files for each chapter. I would recommend going through the different sections of this file before you start working on to understand the available packages and options.
- `filename.tex` these are the .tex file dedicated for individual tasks (such as, title, abstract, references, etc.) or chapters. These files are called from the `00-main.tex` file using an `\include{}` command which flushes all the floating object and start a new page.
- `figures` subdirectory contains all the figures for the thesis. You can add the figures as chapter-wise PDF files or as just individual images with allowable extensions. Images are called using `\includegraphics{}` command in a figure environment. You can also use `\includegraphicx{}` command to avoid using specific image file extension.
- `thesis.bib` file is a biblatex file which contains all the bibliographic items. Use Zotero or some other citation manager to generate the biblatex file containing all the items.
- `latexmkrc` additional settings for the make file to generate PDF/A output. This is required to have in the main directory of Overleaf project.
- `output.xmpdata` contains simple meta-data to be be tagged in the final PDF/A file. Usage of this file is optional and the content inside is self-explanatory.
- `README.md` this file which contains the details related to the template.



## How to use the template on Overleaf

I prefer using Overleaf for all of my LaTeX compilation and I recommend it storngly since Johns Hopkins provides premium account to all students for Overleaf. Premium Overleaf does fast compilation, allows sharing the project with multiple people (advisor, committee members, collaborator, labmates, friends, or family), keep track history which is great. You can recover file if you break it (hopefully you won't). Follow one of the three approaches to get started with this project on Overleaf. Then go through the main file and other files to see how the template is structured.

- To use it directly on Overleaf, [open the template here](https://www.overleaf.com/latex/templates/johns-hopkins-thesis-slash-dissertation-template/gbfnqqfzffyp). Then click on **Open as Template** and proceed from there to go through the template and edit it.

- If the overleaf version is outdated for some reason (Overleaf takes a bit of time to update the templates), then you can download / clone this repository from GitHub, then compress it as a zip file. Go to Overleaf, Click on **New Project** -> **Upload Project**, then upload the zipped folder. Continue...
  
- If you have your Overleaf and GitHub account linked and want to have copies of the project in both places, you can **fork** this repository. Then go to Overleaf, Click on **New Project** -> **Import from GitHub**, it should list the forked project for listing. Once imported, you can start working on Overleaf. But Overleaf and GitHub will not sync automatically; you will have to do it to have updated version on GitHub.

Once you have imported the project, you need to compile `00-main.tex` file using `pdflatex` option (default on Overleaf) which will call all the auxilary files included to produce the final PDF. It should compile without any error on Overleaf. There might be warnings, but you can ignore them. 



## Notes on generating PDF/A compliant output file for JH library

Johns Hopkins Library requires the electronic copy of the thesis should be [generated in PDF/A format](https://www.adobe.com/uk/acrobat/resources/document-files/pdf-types/pdf-a.html) which is not trivial. Compiling LaTeX document is a bit of involved process but thanks to Overleaf that we do not really have to worry about it. [Check here to learn how do they do it](https://www.overleaf.com/learn/how-to/How_does_Overleaf_compile_my_project%3F). I have not done the compilation locally for this project and do not plan on doing it. So I am unable to provide any help in that regard.

- Learn about [latexmkrc file on Overleaf](https://www.overleaf.com/learn/latex/Articles/How_to_use_latexmkrc_with_Overleaf) which you will need to generate PDF/A file.
- [This documentation](https://www.overleaf.com/latex/templates/creating-pdf-slash-a-and-pdf-slash-x-files-with-the-pdfx-package/bbbycnbyqhnm) provides details on how to generate PDF/A compilant output on Overleaf. **Open as Template** to see what is included in the project.
  - Briefly, PDF/A compliant output is generating by including `\usepackage{pdfx}` command in the preamble, and to ensure the compilation worked properly, the project directory needs to include `latexmkrc` input file in which you will need to specify the timezone; [check supported timezones here](https://www.php.net/manual/en/timezones.php).
  - Optionally, to include the meta-data in the generated PDF, you can edit the `output.xmpdata`. The given fields are very simple.



## Some useful comments and suggestions for using the template

Overleaf has a huge collection of tutorials and examples on different LaTeX-related typesetting topics (margins and page size, math, table, footnote, bibliography management). You will most likely to find what you need there. Another useful resource for [writing thesis in LaTeX is here](https://www.khirevich.com/latex/). Some specific suggestions for this template are below:

- Most of the necessary variables to customize the format of the document are included in the beginning of the `00-main.tex` file. You can customize different spacing and style options using these variables. For most cases, tweaking these variables to your need and preference will be more than good enough to get desired format which conforms to library requirement. So, try to understand what each variable does by tweaking them before you start putting your contents in there, and finalize them as needed to customize the dissertation formatting there.

- I prefer using Latin Modern Roman font for documents typeset in LaTeX because the text and math environments have consistent typesetting. You can try other fonts, but you should be careful about being consistent specially for math and text typesettings.

- In addition to these variables, if your bib file has a different name than the current file, then change the `BibFileName` varibale. Make sure to specify the correct name for the `FigurePath` as well.

- Add all the figures in the `figures` subdirectory. If your subdirectory name is different, then change `FigurePath` variable. You can add chapter-wise PDF files (which is what I prefer) or just add all of them as you have them in that directory.

- Currently `nature` (numbered format) and`apa` (author-year format) style options are there for the bibliography. Choose either of them or you can add something else depending on your discipline or department requirement or advisor's suggestion such as IEEE, MLA, Harvard, Chicago, etc. Find where the BibLaTeX package is added to the document and customize the options for the bibliographic package based on the style.
 
- The bibliography file is based on BibLaTeX which is a more modern package compared to BibTeX and natbib. Use Zotero (this is what I use) or some other citation manager to generate a standard BibLaTeX file.

- Most common and popular packages for writing dissertations are added in the `LaTeX CLASS AND PACKAGES` sections. Check the packages; add any additional package you need and/or customize your options there.

- By default, tables are defined to have `\arraystretch{1.5}` (which is equivalent to double-spaced text). If you would like to customize the spacing inside a table globally throughout the document, you can try decreasing/ increasing the varible `GlobalTableSpacing`. However, I suggest doing it locally by defining a group for each table (StackExhange or StackOverflow is your friend here) where you can redefine `\arraystretch` for the individual tables as needed. Also if the table is wider than the page during editing, you may want to use the landscape tables which are placed sideways and may go over multiple pages (someone on StackExhange or StackOverflow has done it for sure).

- Most of the common formatting-related settings are available in the `DOCUMENT FORMATTING` section in the main file. Additional optional settings related to the table of contents, epigraphs, algorithms, and listing packages are separately available but a little bit more complicated. Unless you really want to customize a whole to your taste very spcifically, you can leave them as it is.

- You can also remove the settings for the optional packages that you do not indent to use such as `epigraph`, `listings`, `algorithm2e`, etc. But be careful while doing that; do not break the code.

- If you add a quote before the chapter heading, then you may want to increase the white spacing on top. In this case, all of the Chapters will have white space before Chapter # and title. I personally did not like the default font size and spacing in the LaTeX `report` class. 

- For unnumbered chapters that you want to add to the table of contents, use the `\chap` command instead of the `\chapter*` command. (see, *Abstract* and *Acknowledgment*, for example). An exception to this is *Dedication* chapter because it does not have chapter title.

- Similarly, for unnumbered sections, subsections, and subsubsections that you would like to add to the table of contents, use `\sect`, `\subsect`, and `\subsubsect` commands, respectively. If you do not any of these environments to be added to the table of contents, then you can use standard * environments; such as `\section*{}`, etc.

- Currently, 3 numbered environments `\section{}`, `\subsection{}`, and `\subsubsection{}` are activated throughout the document and available in table of contents. You can decrease or increase thus by tweaking varialbles: `\NoSectionLevel` and `\NoTocLevel`. I personally prefer 2-3 levels for large documents, otherwise it gets too clumsy and confusing.

- Space around the headings of different environments is managed by `parskip` package. I found the default settings to be working fine for me. But if you would like to customize it, you can add following command in the preamble:
  ```
  \titlespacing*{<environment-name>}{<space-left>}{<space-before>}{<space-after>}
  ```
  
- Add your math macros and settings in the `MATH SETTINGS AND MACROS` section. There's a section for non-math `OTHER MACROS` as well. Some examples of both types of macros are added there.

- You can use `\linenumbers` command from `lineno` package anywhere inside the main text document when you would like to have line numbers on the left margin. It might be useful during the drafting stage.

- If you find all the packages and their settings and macros to be overwhelming and distracting during the editing process, you can cut and paste all these contents to a separate `settings.tex` file (name it as you like) in the project directory. Then you can use the command `input{settings.tex}` to make your main file appear cleaner and less distracting. `\input{}` command literally pastes content from the source file. See [managing large project on Overleaf](https://www.overleaf.com/learn/latex/Management_in_a_large_project).

- If the chapter name is too long, you may have to customize the header spacing in the geometry settings options to accommodate that. Tweak the variables `HeaderHeight` and `HeaderSpace` in the variable declaration section. You can add `showframe` option to the `geometry{}` command to see the layout of your document.
  - If you have one or two chapters with long title, changing it locally for individual chapter is a bit tricky task. In that case, you can use header with a short chapter title option. See the examples are given in individual chapters how to add a shorter title. But if it gets difficult to customize or generalize, you can also consider to remove all the header options by commenting them out in the document section of the `00-main.tex` file.

- Finally, you may consider using `microtype` package to have a better typography. Check details on using [microtype package for writing thesis here](https://www.khirevich.com/latex/microtype/).

- Keep writing ... and Happy Graduation :tada:!


## Contributing to the project

This template was kept sufficiently general purpose for different disciplines with some customizations of special packages for demonstration purpose. If you have suggestion about specific LaTeX packages to your preference or discipline, it may not be a good idea to add them here. However, if you have suggestions about general formatting, you can fork the repostiroy and create a `pull request`, or simply just find me and let me know.
