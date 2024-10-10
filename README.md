# Bibliography

A database of scientific references organized in .bib files.


## Installation

The database can be loaded using the `biblatex` package. The recommended commands are:

```latex
\RequirePackage[
  style=numeric-comp,
  sorting=none,
]{biblatex}
\ExecuteBibliographyOptions[proceedings]{skipbib=true}

\addbibresource{src/xdata.bib}
\addbibresource{src/proceedings.bib}
\addbibresource{src/books.bib}
\addbibresource{src/articles.bib}
```

The option `doi=false` can also be used to exclude DOI from the bibliographic entries. However, it is advised to use the shortDOi Service to shorten long DOI instead.


## Compatibility

If `biblatex` is not supported by the document class, `biber` can be used to provide direct `BibTex` support:

```powershell
  biber --output-format=bibtex --output-legacy-dates --output-field-replace=[journaltitle:journal] main
```


## License

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg