# TeX-TikZ-slow-MWE

Introduction
===
Hello, I am facing very long compile times for a ~130 page document, including around 40 PGF-Plots/TikZ-Images. Due to LaTeX's memory limits and (in fact) for speed up reasons, I decided to use the `external`-package. 

Then I noticed, that each image takes up to 25 seconds to render (looking into my `pdflatex.log` from Miktex 2.9.

**I created a MWE for demonstrating this effect, which seems to increase with the number of other packages loaded:

[TeX-TikZ-slow-MWE.tex](TeX-TikZ-slow-MWE.tex)**

[![MWE Output][2]][2]

This example gives me the two respective `pdflatex.log`-Files, depending on whether externalization is enabled or disabled:

Externalization enabled
---
**Total time: ~14.0 s**

    2019-03-05 13:21:31,240+0100 INFO  pdflatex - starting with command line: pdflatex.exe -synctex=1 -interaction=nonstopmode -enable-write18 TeX-TikZ-slow-MWE.tex
    2019-03-05 13:21:31,246+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:21:31,246+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:21:31,246+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:21:33,607+0100 INFO  pdflatex - executing write18 shell command: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname "figtemp/TeX-TikZ-slow-MWE-figure0" "\def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}"
    2019-03-05 13:21:33,885+0100 INFO  pdflatex - starting with command line: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname figtemp/TeX-TikZ-slow-MWE-figure0 \def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}
    2019-03-05 13:21:33,891+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:21:33,891+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:21:33,891+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:21:36,177+0100 INFO  pdflatex - finishing with exit code 0
    2019-03-05 13:21:36,326+0100 INFO  pdflatex - executing write18 shell command: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname "figtemp/TeX-TikZ-slow-MWE-figure1" "\def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}"
    2019-03-05 13:21:36,614+0100 INFO  pdflatex - starting with command line: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname figtemp/TeX-TikZ-slow-MWE-figure1 \def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}
    2019-03-05 13:21:36,619+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:21:36,620+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:21:36,620+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:21:39,167+0100 INFO  pdflatex - finishing with exit code 0
    2019-03-05 13:21:39,311+0100 INFO  pdflatex - executing write18 shell command: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname "figtemp/TeX-TikZ-slow-MWE-figure2" "\def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}"
    2019-03-05 13:21:39,583+0100 INFO  pdflatex - starting with command line: pdflatex -enable-write18 -halt-on-error -interaction=batchmode -jobname figtemp/TeX-TikZ-slow-MWE-figure2 \def\tikzexternalrealjob{TeX-TikZ-slow-MWE}\input{TeX-TikZ-slow-MWE}
    2019-03-05 13:21:39,592+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:21:39,592+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:21:39,592+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:21:41,817+0100 INFO  pdflatex - finishing with exit code 0
    2019-03-05 13:21:42,029+0100 INFO  pdflatex - finishing with exit code 0
    2019-03-05 13:21:42,485+0100 INFO  pdflatex - starting with command line: pdflatex.exe -synctex=1 -interaction=nonstopmode -enable-write18 TeX-TikZ-slow-MWE.tex
    2019-03-05 13:21:42,489+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:21:42,489+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:21:42,489+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:21:45,223+0100 INFO  pdflatex - finishing with exit code 0

Externalization disabled
---
**Total time: ~5.1 s**

    2019-03-05 13:23:19,734+0100 INFO  pdflatex - starting with command line: pdflatex.exe -synctex=1 -interaction=nonstopmode -enable-write18 TeX-TikZ-slow-MWE.tex
    2019-03-05 13:23:19,742+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:23:19,742+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:23:19,742+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:23:22,045+0100 INFO  pdflatex - finishing with exit code 0
    2019-03-05 13:23:22,476+0100 INFO  pdflatex - starting with command line: pdflatex.exe -synctex=1 -interaction=nonstopmode -enable-write18 TeX-TikZ-slow-MWE.tex
    2019-03-05 13:23:22,485+0100 INFO  pdflatex - allowing known shell commands
    2019-03-05 13:23:22,485+0100 INFO  pdflatex - enabling input (output) from (to) processes
    2019-03-05 13:23:22,485+0100 INFO  pdflatex - allowing all shell commands
    2019-03-05 13:23:24,842+0100 INFO  pdflatex - finishing with exit code 0

Conclusion
===
Externalizing my three (very simple) TikZ-Images blows up compilation time almost by a factor of 3. 

(This Question was asked here on [TeX-SE][3])


  [1]: https://github.com/pfedan/TeX-TikZ-slow-MWE
  [2]: https://i.stack.imgur.com/GeTR8.png
  [3]: https://tex.stackexchange.com/questions/477859/externalizing-tikz-images-takes-very-long
