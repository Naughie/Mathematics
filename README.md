# About
This repository consists of these files:

- `math.tex` (the root file)
- `packages.tex` (all `\usepackage`)
- `my_commands.tex` (global macros)
- `*.tex` (the other source file)
- `biblio.bib` (the bib file)
- `math.pdf` (the output file)

To compile this via `uplatex`, run `latexmk math.tex` with a `.latexmkrc` like:

```perl
#!/usr/bin/env perl
$latex = 'uplatex -synctex=1 -halt-on-error';
$latex_silent = 'uplatex -synctex=1 -halt-on-error -interaction=batchmode';
$bibtex = 'upbibtex';
$dvipdf = 'dvipdfmx %O -o %D %S';
$makeindex = 'mendex %O -o %D %S';
$max_repeat = 5;
$pdf_mode = 3;

$pvc_view_file_via_temporary = 0;
$pdf_previewer = 'open -ga /Applications/Skim.app';
```

If you would like to typeset via `lualatex`, run `latexmk -lualatex math.tex`.
An engine other than `uplatex` and `lualatex` may not work well. In the future, I will support `xelatex`, `platex` and `pdflatex` as well.
