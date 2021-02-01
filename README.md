# latex
LaTeX and Beamer related discussions

LaTeX: [tutorial](https://www.latex-tutorial.com/tutorials/)  
[Overleaf](overleaf.com) - an online LaTeX editor  
[Latexsheet](http://wch.github.io/latexsheet/latexsheet-a4.pdf)  

**Note on Bibliography**  
Make sure .tex (mani latex source), .bib (bibliography entries), and .bst (bibliography style) files are in the same directory. The following sequence can be handy. 

```
\documentclass{article}
%\documentclass{cta-author}

% premble for packages
\usepackage{hyperref}

% add bibliographystyle required for example iet.bst
\bibliographystyle{iet}

\title

\begin{abstract}
\end{abstract}

\begin{document}

\maketitle

\section
...

% add bibliography .bib file name without file extension .bib
\bibliography{mybib}

\end{document}
```

At times, what you see and what you get in LaTeX, defies the logic :)  
It can consume a lot of time, especially while switching between journal formats.  

If cited publications using \cite{someindex} are not appearing under References, or you are getting an [empty .bbl file](https://tex.stackexchange.com/questions/207664/bibtex-generates-an-empty-bbl-file), rename both .tex and .bib file to all small letters and same name with different extensions. Do not forget to update filename in .tex file using \bibliography{filename}. 
