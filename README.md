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

\addbibresource{src/xdata/macros.bib}
\addbibresource{src/xdata/countries.bib}
\addbibresource{src/xdata/organizations.bib}
\addbibresource{src/xdata/journals.bib}
\addbibresource{src/xdata/authors.bib}
\addbibresource{src/proceedings.bib}
\addbibresource{src/books.bib}
\addbibresource{src/articles.bib}
\addbibresource{src/pre-prints.bib}
```

The option `doi=false` can also be used to exclude DOI from the bibliographic entries. However, it is advised to use the shortDOi Service to shorten long DOI instead.


## Compatibility

If `biblatex` is not supported by the document class, `biber` can be used to provide direct `BibTex` support:

```bash
  biber --output-format=bibtex --output-resolve main
  sed -i -E "s/(DATE = \{[0-9]{4}-[0-9]{2})[0-9,-]+\}/\1\}/" main_biber.bib
  biber --tool --output-legacy-dates --output-field-replace=journaltitle:journal main_biber.bib
  rm main_biber.bib
  mv main_biber_bibertool.bib bibliography.bib
```


## License

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg