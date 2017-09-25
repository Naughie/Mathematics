# About
This repository consists of these files:

- `root.tex` (the root file)
- `packages.tex` (all `\usepackage`)
- `pref.tex` (preferences)
- `commands.tex` (commands used in a document)
- `*.tex` (the other source file)
- `biblio.bib` (the bib file)
- `math.pdf` (the output file)

To compile this via `uplatex`, run `latexmk root.tex` with a `.latexmkrc` like:

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

If you would like to typeset via `lualatex`, run `latexmk -lualatex root.tex`; if `xelatex`, run `latexmk -xelatex root.tex` (it may halt on error with `xelatex`).

Supported engines:

- `uplatex`,
