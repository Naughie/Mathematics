#About
This repository consists of these file:

```
math.tex #the root file
packages.tex #all \usepackage
my_commands #global macros
*.tex #the other source file
biblio.bib #the bib file
math.pdf #output file
```

To compile this, run `latexmk math.tex` with a `.latexmkrc` like:

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
$pdf_previewer = 'open -ga /Applications/Skim.app'
```
An engine other than `uplatex` may not work well. In the future, I will support `lualatex` as well.
