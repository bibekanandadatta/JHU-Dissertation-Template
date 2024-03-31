# JHU Thesis or Dissertation Template

This is an unofficial thesis (masters) or dissertation (PhD) template for Johns Hopkins with recent updates by Bibekananda Datta. This template is created to be used on Overleaf and the compilation details are given below. However, you can compile it locally on your computer as well if you already know how to do it, but not within the scope of this README file.

As of March 2024, the template follows the thesis or dissertation formatting requirements provided by the [Johns Hopkins University Sheridan Library](https://www.library.jhu.edu/library-services/electronic-theses-dissertations/formatting-requirements/). Johns Hopkins Library is flexible in terms of the format except for the title page, margins, and overall double-spaced content. **However, be sure to check the requirements before you proceed any further. It is the user's responsibility to ensure all the formatting requirements are met.**


## Table of Contents

* [Version history for the template](#version-history-for-the-template)
* [What is included in this version of the template](#what-is-included-in-this-version-of-the-template)
* [How to use the template on Overleaf](#how-to-use-the-template-on-overleaf)
* [Document formatting (customization beyond the requirements)](#document-formatting-customization-beyond-the-requirements)
* [Basic user guidelines](#basic-user-guidelines)
  + [Title page](#title-page)
  + [Prefaces and TOC, LOT, LOF, etc.](#prefaces-and-toc-lot-lof-etc)
  + [Main text](#main-text)
  + [Figures, Tables, and Algorithms](#figures-tables-and-algorithms)
  + [Bibliography](#bibliography)
  + [Generating PDF/A compliant output file for the JH Library on Overleaf](#generating-pdfa-compliant-output-file-for-the-jh-library-on-overleaf)
* [Contributing to the project](#contributing-to-the-project)


## Version history for the template

- The report-class-based template was first created by R. Jacob Vogelstein in May 2007
- Updated by Noah J. Cowan on March 01, 2010
- Updated by Brian D. Weitzner on April 29, 2014 
- Updated by John Muschelli on January 29, 2016 
- Updated by Leonardo Collado Torres on April 13, 2016 
- Updated by John Clayton in December 2019
- The current version is updated by Bibekananda Datta on March 30, 2024


The previous version of the template used default options for the LaTeX report class and different packages which had unusually large font sizes and extra white spaces around different environments. So, I decided to reorganize the template and add more customization by loading the necessary packages. Compared to the previous version, for the current version of the template, I have:

  - reorganized the code in the template in a more readable and understandable format.
  - formatted the title page following the library guidelines strictly.
  - added custom macros to generate title page and front matters (TOC, LOT, LOF).
  - updated the appearance of the table of contents, list of figures, and list of tables.
  - added customization options to control the font size and shape of different headings.
  - added customization options to control the white space for different environments.
  - added specific settings for adding quotes (epigraph package) to the chapters.
  - added examples of customized macros for mathematical and non-mathematical environments.
  - added support to generate PDF/A output on Overleaf directly.


### Future task list
- [ ] Add documentation for different font and bibliographic styles
- [ ] Add additional listing environments for algorithms, codes, acronyms, supplementary materials, glossaries, etc.
- [ ] Extend the document styling for paragraph and subparagraph environments and their appearance in TOC.



## What is included in this version of the template

Since the template is based on the report class, it is subdivided into multiple chapters. There are separate .tex files for all the front matters (mandatory or optional), technical chapters, and back matters (references and appendices).

| File name   | Description   |
| :---------  | :-----------  |
| `00-main.tex` | file is the driver or root file which includes all the preamble, document settings, package settings, and macros as needed as well as the auxiliary .tex files for each chapter. I would recommend going through the different sections of this file before you start working to understand the available packages and options. |
| `<filename>.tex` | are the `.tex` files dedicated to individual pages (e.g., title, dedication) or environments (such as abstract, bibliography, etc.) or technical chapters. These files are called from the `00-main.tex` file using an `\include{}` command which flushes all the floating objects and starts a new page. |
| `figures` | is the subdirectory containing all the figures for the thesis. You can add the figures as chapter-wise PDF files or as just individual images with allowable extensions. Images are called using the `\includegraphics{}` command in a figure environment. |
| `thesis.bib` | is a biblatex file that contains all the bibliographic items. Use Zotero, Mendeley, EndNote, or some other citation manager to generate the biblatex file containing all the bibliographic items. |
| `latexmkrc` | contains additional settings for the make file to generate PDF/A output. This is required to be in the main directory of the Overleaf project. |
| `output.xmpdata` | contains simple meta-data to be tagged in the final PDF/A file. Usage of this file is optional and the content inside is self-explanatory. |
| `template_example.pdf` | is the sample output PDF that you will obtain when you start working on this project. |
| `README.md` | is this file that contains the details related to the template. |



## How to use the template on Overleaf

I prefer using Overleaf for all of my LaTeX compilation and I recommend it strongly since Johns Hopkins provides the Overleaf premium account to all students. Overleaf Premium does fast compilation, allows sharing the project with multiple people (advisor, committee members, collaborator, labmates, friends, or family), allows reviews, comments, and chat options, and tracks histories which are great features to boost productivity. You can recover the files if you break them (hopefully you won't). Follow one of the two approaches to get started with this project on Overleaf. Then go through the `00-main.tex` file and other files to see how the template is structured.

- If the Overleaf version is outdated for some reason (Overleaf takes a bit of time to update the templates), then you can download/clone this repository from GitHub, and compress it as a zip file. Go to Overleaf, Click on **New Project** -> **Upload Project**, then upload the zipped folder.
  
- If you have your Overleaf and GitHub account linked and want to have copies of the project in both places, you can **fork** this repository. Then go to Overleaf and click on **New Project** -> **Import from GitHub**, it should list the forked project. Once imported, you can start working on it. But Overleaf and GitHub will not sync automatically; you have to do it to have an updated version on GitHub.

- Once you have imported the project, you need to compile the `00-main.tex` file using the `pdflatex` option (default on Overleaf) which will call all the auxiliary `.tex` files included to produce the final PDF. It should compile without any error on Overleaf. There might be warnings, but you can ignore them. 

> [!NOTE]
>
> This template is not available on Overleaf Gallery as it takes time to release any updates made by me and especially does not endorse making small patches or updates. This is also not available as a class on CTAN since it will require the user to have access to the most updated version of LaTeX distribution and frequent updates will be difficult.

> [!TIP]
>
> Although it is very convenient to write your document on Overleaf, strongly consider backing up your work using Git or GitHub integration or the Dropbox sync feature. This may save you from losing your document in case of an accident.



## Document formatting (customization beyond the requirements)

As mentioned before, the template is based on the standard report class. However, I found the default formatting of the LaTeX report class (even with different packages) has disproportionate font sizes and spacing for different environments which led me to the customization while maintaining the requirements. Look into this first to understand [how space is managed in LaTeX](https://www.overleaf.com/learn/latex/Articles/How_to_change_paragraph_spacing_in_LaTeX).

- The document was typeset using Latin Modern Roman font (loaded using the `lmodern` package) for document typeset as it offers consistent typesetting between the text and math environments.

- The font size for the main text of the document is set to 12 pt and is overall double-spaced (library requirement).

- The title page is single-spaced and items were positioned within the page following library guidelines.

- All the texts in the preface chapters and the main text chapters are double-spaced.
  - You can define local environments in optional preface chapters (acknowledgement, dedication, epigraph, etc.) which have different styles and spacing.

- For different text environments and their headings, relative font sizes are used as given below. Learn about [LaTeX font size here](https://www.overleaf.com/learn/latex/Questions/How_do_I_adjust_the_font_size%3F).
  - For the thesis title and chapter label and title, I used `\Large\bfseries\MakeUppercase` (**boldface 17.28 pt**).
  - For the section headings, I used `\singlespacing\large\bfseries` (**boldface 14.4 pt**) whereas, for the subsection headings, I used `\normalsize\bfseries` (**boldface 12 pt**).
  - For the subsubsection headings, I used `\normalsize\itshape` (*italic 12 pt*).
  - For the table and figure captions, I used `\small` (10.95 pt).
  - For the footnotes, I used the default `\footnotesize` (10 pt), and footnote texts are single-spaced with `\baselineskip` spacing between each footnote.


- The texts of the Table of Contents (TOC), List of Tables (LOT), and List of Figures (LOF) in the front matter, and bibliographic references in the back matter are single-spaced.
  - Spacing between two consecutive chapter entries in the TOC is `\baselineskip`. For two consecutive sections, it is `0.5\baselineskip`, and for subsections and subsubsections, the space is `0.3\baselineskip`.
  - Spacing between two consecutive bibliographic items in the bibliographic reference section in the back matter is `\baselineskip`.

- Spacing around the headings of different text environments is the default spacing provided by the `parskip` package.

- Chapter labels are placed approximately 1.5 inches from the top of the page followed by the chapter title in the next line with an approximate spacing of 0.3 inches in between them.
  - Space between the chapter title and the following text is approximately 0.75 inches except for the case when there is a quote. In the latter case, the space followed by the chapter title to the quote and the quote to the following text is 0.5 inches.

- The header and footer are placed outside of the margin. The header includes the chapter label and chapter name whereas the footer includes pagination.
  - The height of the header is 18 pt with 12 pt additional space for the following text. But if you have a long chapter title you may have to change it (details are described later).

- Currently, the document is formatted to have **three** levels of paragraph-style environments (section, subsection, subsubsection) for writing. All of them are shown in the Table of Contents as well.


- The spacing around the section, subsection, and subsubsection headings are chosen to be default offered by the `parskip` package. The paragraphs do not have any indentation with `\baselineskip` spacing in between them.

- Equation numbers are also preceded by chapter numbers as defined by the following command:
  ``` latex
  \numberwithin{equation}{chapter}       
  ```

- The default spacing between rows inside a table environment is one-half-spaced.
  
- Captions for the table and figure environments are placed at the bottom of the environments. The caption starts with boldfaced **Figure** and **Table** labels, respectively, for Figure and Table, and uses chapter-wise numbering separated by a period between the chapter label and the number of the corresponding environment followed by a colon before the long caption.

- Default bibliography style is numbered-based `Nature` style citation. Depending on the discipline, you may have to change it; the details are given below. 



## Basic user guidelines

Overleaf has a huge collection of tutorials and examples on different LaTeX-related typesetting topics (margins and page size, math, table, footnote, and bibliography management). You will most likely find what you need there. Another useful resource for [writing thesis in LaTeX is here](https://www.khirevich.com/latex/). If you would like to do something specific, your best friend is Google; most likely someone on [TeX StackExchange](https://tex.stackexchange.com) has done it before.


The preamble section of the `00-main.tex` file has been subdivided into multiple sections to make the code understandable and readable. A simple descriptions of the sections are below:

- Most of the necessary variables to customize the format and the style of the document are included at the beginning of the `00-main.tex` file in the `LIST OF VARIABLES FOR FORMATTING` section. You can customize different spacing and font style options using these variables. For most cases, tweaking these variables to your needs and preferences will be enough to get the desired formatting. However, some of these variables have values that may appear arbitrary to the user. Those are found by *trial and error* to have a consistent formatting (described above) overriding default formatting offered by the LaTeX report class and added packages.
    
- The most common and popular packages for writing a thesis or dissertation are added in the `LaTeX CLASS AND PACKAGES` sections. Some packages are loaded with the options specified for formatting purposes. For some other packages, options are specified in the `PACKAGE OPTIONS` section. Before you add a package, please check if it has already been added. Sometimes adding packages in the wrong order may throw a warning or error because of the dependency issue.

- Based on the declared variables and loaded package options, formatting-related customized settings are available in the `DOCUMENT FORMATTING` section in the `00-main.tex` file.

> [!TIP]
> 
> If you change any formatting or do further customization, one of the best possible ways to check consistency in spacing is to load the `fgruler` package as below in the preamble (you can change the options by looking into the documentation of this package).
``` latex
\usepackage[unit=in,type=upperleft,color=red,showframe]{fgruler}
```

> [!WARNING]
>
> Finding a different font that offers consistent text and math typography may require you to add customized commands/ macros and options. 

- If you do not like the default font of this template (Latin Modern Roman), you can try a different font or combination of fonts. However, you should be careful about having consistent typesetting, especially between math and text. [Follow this old discussion on StackExchange to learn more about fonts in LaTeX](https://tex.stackexchange.com/questions/59702/suggest-a-nice-font-family-for-my-basic-latex-template-text-and-math).
  - This TUG page lists [fonts that provide math support](https://tug.org/FontCatalogue/mathfonts.html). But Overleaf may not have all of the packages listed there, and some of the packages may raise conflict with other packages that are already loaded. You can try and figure out which works best for you.
  - The font package has been loaded using the `\usepackage{\FontPackage}` command in the `DOCUMENT FORMATTING` section of the preamble. Depending on the Font you choose, you may have to add additional options/ packages (follow the above webpage) and simply changing the `\FontPackage` variable may not work.

- Add your math macros and settings in the `MATH MACROS` section. There's a section for non-math `OTHER MACROS` as well. Some examples of both types of macros are added there in the template.


- Inside the `\begin{document} ... \end{document}` environment, the title page, and other front matters (abstract, dedication, etc.), technical chapters, bibliography chapter, and appendix chapters are added using the `\include{ }` statement. There is no separate chapter for TOC, LOT, LOF, etc., and additionally, headers are customized based on the type of chapter (numbered vs. unnumbered).

> [!TIP]
>
> If you find all the packages and their settings and macros to be overwhelming and distracting during writing and editing, you can cut and paste all these contents to a separate `my-preamble.tex` file (name it as you like) in the project directory. Then you can use the command `\input{my-preamble.tex}` to make your main file appear cleaner and less distracting. See [managing a large project on Overleaf](https://www.overleaf.com/learn/latex/Management_in_a_large_project).


> [!NOTE]
> 
> Currently, the chapters are filled with randomly generated text by the `blindtext` package. Remove them to get started with your writing.


### Title page

The thesis title page is defined using the `titlepage` environment which is centered and single-spaced with no header and footer. To format the title page of the thesis as per the requirement, the following macros are defined:
- `\ThesisTitle:` prints out the **thesis title** approximately 1.5 inches below the top of the page.
- `\ThesisAuthor{}:` prints out the "by author-name" in two single-spaced lines. The author's name is the input argument to the macro.
- `\ThesisStatement{ }{ }:` prints out the thesis or dissertation statement. Arguments to this macro are document type (thesis or dissertation) and degree name without specifying the major.
- `\Location:` prints out the location (Baltimore, Maryland).
- `\ThesisDate{ }{ }:` prints the thesis submission month and year; these are the two arguments to the macro.
- `\ThesisCopyright{ }{ }:` prints the optional copyright statement 2 inches from the bottom of the page. The first and second arguments to this macro are Year and Author name. 


### Prefaces and TOC, LOT, LOF, etc.

- Except for the Abstract, other contents in the front matter can be arbitrarily spaced. For now, the Acknowledgment and Dedication pages are also double-spaced. However, a local `spacing` environment can be used for specialized preface pages to include quotes or dedication, etc.

- All of the contents in TOC, LOT, and LOF are hyperlinked using the `linktoc=all` option in the `\hypersetup{}`. You can change this option to remove hyperlinks in TOC or just hyperlink the pages, etc. You can also change the color of the hyperlink for TOC (currently it is black) while any other hyperlink throughout the document has a blue color.
  - You can define a new color for this using the `xcolor` package (see below) and change the option in `\hypersetup{}`.

- Three different simple macros are defined to print the Table of Contents, List of Tables, and List of Figures in that order. These macros were defined to extend the functionalities (title change, appearance in the TOC, proper page numbering, etc.) of the default commands of similar kinds offered by LaTeX. Using the default LaTeX commands for TOC, LOT, and LOF perhaps won't serve your purpose.
  - `\mytableofcontents:` to print the table of contents.
  - `\mylistoftables:` to print the list of tables.
  - `\mylistoffigures:` to print the list of figures.

- Currently, the template does not have any specific settings or package options to print the List of Algorithms, List of Supplementary Materials, the List of Abbreviations, and the List of Symbols, etc. However, you can look into `glossaries`, `glossaries-extra`, and `tocloft` packages to define custom lists to be printed. This might take a little bit of time to do.



### Main text

- You can add quotes to the chapter followed by the chapter label and title using the `epigraph` package. Examples are shown in two different chapters of the template.
  - Currently, the maximum length for the epigraph is set to be `0.65\textwidth` which can be changed by specifying the variable `\MaxQuoteWidth`. You can make it shorter or longer depending on your needs and/or preferences.
  - If you have a longer quote that spans over multiple lines and you are not happy with the default `doublespacing` you can customize it using a spacing environment around the quote (same as the chapter citation declaration, see below) to make it appear consistent.
    ``` latex
    \begin{spacing}{<some-spacing-value>}
      \epigraph{\enquote{quote-goes-here}}{quote-author}
    \end{spacing}
    ```
  - You can also add quotes before the chapter labels and titles (instructions are included inside the chapter), but in that case, you have to change the `\ChapterTopMargin` variable to ensure enough spacing before the chapter label and it may complicate the overall document formatting (not recommended).


- If any chapter is already published at a journal or conference or available in any of the archival repositories (submitted/ to be submitted to a peer-reviewed journal/conference), it is a good idea to declare it at the beginning of the chapter. Such an example has been shown in Chapter 2 of the template. To have consistent formatting, a `singlespace` environment was used, and the publication was printed with the `\fullcite{}` command. 
  - If the chapter is adapted from multiple publications, you can use `enumerate` or `itemize` environments to list all the publications inside the spacing environment.
  - If the listed paper (published, submitted, or in preparation) is not cited anywhere else in the document and you do not want this to appear in the bibliographic references in the back matter, then use the following command. This command adds the paper to the group called `mypapers` which are not printed in the bibliography list. You can place the command anywhere; maybe in the reference chapter before printing the reference when you are sure about which bib items should not be included.
    ``` latex
    \mybibexclude{citation-key}
    ```

  
- For unnumbered chapters that you want to add to the table of contents, use the `\chap` command instead of the `\chapter*` command. (see, *Abstract* and *Acknowledgment*, for example). An exception to this is *Dedication* chapter because it does not have a chapter title.

- Similarly, for unnumbered sections, subsections, and subsubsections that you would like to add to the table of contents, use `\sect`, `\subsect`, and `\subsubsect` commands, respectively. If you do not any of these environments to be added to the table of contents, then you can use standard * environments; such as `\section*{}`, etc.

- Currently, **three** numbered *paragraph environments*, `\section{}`, `\subsection{}`, and `\subsubsection{}`, are available throughout the document and shown in the TOC. You can decrease or increase this by tweaking variables, `\NoSectionLevel` and `\NoTocLevel`.
  - For such a complicated and long document, it is perhaps not a good idea to have more than three levels of paragraphs in the main text section.
  - LaTeX report class offers `\paragraph` and `\subparagraph` levels as 4th and 5th level. In case you would like to include those in your document, you will have to configure the styles for them and their appearance in the TOC.

- To override the default spacing from the `parskip` package around the headings of different environments, the `titlesec` package can be used. To customize it, add the following command in the preamble (use pt as the units). You may have to do a bit of *trial and error* to find consistent spacing.
  ``` latex
  \titlespacing*{<environment-name>}{<space-left>}{<space-before>}{<space-after>}
  ```
  
- Header and footer options in the document are managed using the `\fancyhdr` package. Currently, the header prints the chapter label and the chapter title on the left side. If the chapter name is too long, you may have to customize the header spacing in the geometry settings options to accommodate that. Tweak the variable `\HeaderHeight` for this. The current value is set to `30 pt` which can accommodate double-line headers.
  - If you have even longer consider changing the `\HeaderHeight` from `30 pt` (for double lines) to `42 pt` (for triple lines).
  - You can also consider making the font size smaller for the headers.
  - Alternatively, you can consider including a shorter chapter title which will be printed as the header by starting the chapter environment as follows:
    ``` latex
    \chapter[short-chapter-name]{long-chapter-title}
    ```
  - If customizing the header becomes too difficult, you can also consider removing all the header options by commenting them out in the document section of the `00-main.tex` file. In that case, remove the `includehead`, `headheight`, and `headsep` options from the `\geometry{ ... }` command in the `PACKAGE OPTION` section.
  - In case, you would like to see the layout of your document, then you can add the `showframe` option to the `\geometry{ ... }` command to see the layout of your document. This is a simpler alternative to the `fgruler` package but you will not see a ruler.

- To list items, use `enumerate` and `itemize` environments. But make sure to customize the spacing to have consistent typography with the double-spaced text document.

- You can add algorithms using the `algorithm2e` package, and codes using the `listings` and `minted` packages. Customize these packages to your needs/preferences.

- You can use the `\linenumbers` command from the `lineno` package anywhere inside the main text document when you would like to have line numbers on the left margin. It might be useful during the drafting stage. Currently, this package is loaded with the `pagewise` line numbering option.

- To use colors in your writing (such as hyperlinking or text coloring) or drawing, you can consider using the `xcolor` package with the `dvipsnames` option (already loaded with this option in the preamble). Check [how to use colors in LaTeX on Overleaf](https://www.overleaf.com/learn/latex/Using_colors_in_LaTeX).

- Finally, you may consider using the `microtype` package to have better typography. Customizing the settings for this package is a bit of an involved process and requires some effort, hence not included in the template. To understand and appreciate microtypography, check the details on using [microtype package for writing a thesis here](https://www.khirevich.com/latex/microtype/).
  - It is best not to use the `protrusion` option from the `microtype` package for the TOC, LOT, and LOF. So if you use this package, you may need to set the `protrusion` option to `false` before those environments and set it back to `true` after those environments.


### Figures, Tables, and Algorithms

- Add all the figures in the `figures` subdirectory. If your subdirectory name is different, then change the `FigurePath` variable. You can add chapter-wise PDF files (which is what I prefer) or just add all of them as you have them (PNG or JPG) in that directory.
  - For large figures, you can consider adding them in landscape mode using the `sidewaysfigure` environment from the `rotating` package
  - Regardless of the file extension and program you use to produce the figure, it is a good practice to ensure the fonts within the images are embedded.

- If you would like to customize the spacing inside a table globally throughout the document, you can change the variable `\GlobalTableSpacing`. However, I suggest doing it locally by defining a group for each table (StackExhange or StackOverflow is your friend here) where you can redefine `\arraystretch` for the individual tables as needed.
  - For wide tables, you can use the `sidewaystable` environment from the `rotating` package which will print our table in landscape mode. However, the pagination should always appear at the bottom center of the page, make sure not to change it.

- For algorithms and pseudocodes, the `algorithm2e` package has been loaded as it is the most flexible (provides a lot of customization options) and updated package. In case you already have your algorithm typeset using a different package, change the package. To learn more about algorithm-related LaTeX packages, [see here](https://www.overleaf.com/learn/latex/Algorithms).
  - Similar to the figures and tables, you can print the list of algorithms in the front matter of your thesis. However, to have a consistent formatting of this similar to the other listings, you will need to define macros.



### Bibliography

- The name of your bib file has to be specified in the `BibFileName` variable in the `LIST OF VARIABLES FOR FORMATTING` section. If your bib file has a different name than the given file, then change the variable name or the file name.


- The bibliography file is based on BibLaTeX which is a more modern and flexible package compared to BibTeX and natbib. Consider using Zotero, Mendely, EndNote, or some other citation manager to generate a standard BibLaTeX file.
  - To change the default form of the bibliography (currently, `Nature` style), look for the following command and change the options based on your need and/or preference. Depending on the discipline, you may need to use different citation formats such as IEEE, ACM, APA, ACS, AIP/ APS, AMS, MLA, Harvard, etc. As an example, APA styles are also shown in the template as well (commented). Customization can be done by changing options within `[ ... ]` of the following command.
    ``` latex
    \usepackage[ ... ]{biblatex}
    ```
  - For other citation styles, you may have to scavenge through the internet a little bit to have a properly formatted bibliography. Learn more about the [citation styles in BibLaTeX](https://www.overleaf.com/learn/latex/Biblatex_citation_styles) and check out [biblatex-related packages on TUG](https://ctan.org/topic/biblatex).


- Bibliographic references are printed using the following command which will ensure the citations included in the `\mybibexclude{}` command are not printed.
  ``` latex
  \printbibliography[heading=none,notcategory=mypapers]
  ```

> [!CAUTION]
>
> The `biblatex` package works differently than the older `bibtex` package (which is still available). Make sure you generate the `.bib` file compatible with the `biblatex` package, not the `bibtex` package. If you are required to add a particular citation style that can not be configured using `biblatex` package at all, then consider removing the options related to it, and then add the package and option related to the `bibtex` package. However this may break down the LaTeX code (not recommended).


> [!NOTE]
>
> Sometimes even if you have done everything right after fixing an error, Overleaf still may not compile your files because of the auxiliary files in the `cache`. In that case, click on the `Logs and Output Files` option beside the `Recompile` button, then click on the `Clear cached files` button at the bottom, and `Recompile` the files again.


### Generating PDF/A compliant output file for the JH Library on Overleaf

Johns Hopkins Library requires the electronic copy of the thesis must be [generated in PDF/A format](https://en.wikipedia.org/wiki/PDF/A) which is not a trivial task. Even compiling LaTeX documents is a bit of an involved process but thanks to Overleaf we do not have to worry about it. For fun, you can [check here to learn how they do it](https://www.overleaf.com/learn/how-to/How_does_Overleaf_compile_my_project%3F). I have not done the compilation locally for this project and do not plan on doing it. So I am unable to provide any help in that regard.

- Learn about [latexmkrc file on Overleaf](https://www.overleaf.com/learn/latex/Articles/How_to_use_latexmkrc_with_Overleaf) which you will need to generate PDF/A file.
- [This documentation](https://www.overleaf.com/latex/templates/creating-pdf-slash-a-and-pdf-slash-x-files-with-the-pdfx-package/bbbycnbyqhnm) provides details on how to generate PDF/A compilant output on Overleaf. Click on **Open as Template** to see the instructions.
  - Briefly, PDF/A compliant output is generated by including `\usepackage{pdfx}` command in the preamble, and to ensure the compilation worked properly, the project directory needs to include `latexmkrc` input file in which you will need to specify the timezone; [check supported timezones here](https://www.php.net/manual/en/timezones.php). This is already set and you will not need to make any changes.


> [!IMPORTANT]
> 
> To include the meta-data in the generated PDF/A file, you will need to edit the `output.xmpdata`. The given fields are very simple and self-explanatory.


> [!NOTE]
>
> So far, I have not found any convenient way of validating if the generated PDF is compliant with the library-specified PDF/A format for free. The library has computers with Adobe Acrobat Pro installed that can validate the format of the electronic copy of your thesis. If you or your lab has a license to this program, you can do it there as well. Finally, if you find it is not compliant (for any unknown reason), this program will also allow you to convert the format.


Keep writing ... and Happy Graduation :tada:!


## Contributing to the project

This template was kept sufficiently general purpose for different disciplines with some customizations of special packages for demonstration purposes. If you have suggestions about specific LaTeX packages to your preference or discipline, adding them here may not be a good idea. However, if you have suggestions about general formatting, you can fork the repository and create a `pull request` or just find me and let me know.
