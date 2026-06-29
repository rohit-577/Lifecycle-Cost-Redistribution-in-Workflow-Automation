# Paper Source Files

This directory contains the LaTeX source files for the paper.

## Contents

The following files should be placed here:

- `main.tex` — Main LaTeX document
- `acmart.cls` — ACM conference proceedings class file
- `references.bib` — Bibliography file
- `figures/` — Figure source files
- `tables/` — Table source files

## Compilation

To compile the paper:

```bash
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

## Note

The LaTeX source files are available from the author upon request. The published PDF is available in `paper/pdf/`.
