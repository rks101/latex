# latex
LaTeX and Beamer related discussions

LaTeX: [tutorial](https://www.latex-tutorial.com/tutorials/)  
[Overleaf](overleaf.com) - an online LaTeX editor  
[Latexsheet](http://wch.github.io/latexsheet/latexsheet-a4.pdf)  

**Note on Bibliography**  
Make sure .tex (mani latex source), .bib (bibliography entries), and .bst (bibliography style) files are in the same directory. The following sequence can be handy. 

```
\documentclass{article}

% premble for packages
\usepackage{amsmath}      % for dealing with mathematics
\usepackage{amsthm}       % for dealing with theorem environments
\usepackage{hyperref}     % for linking the cross references
\usepackage{graphics}     % for dealing with figures
\usepackage{algorithmic}  % for describing algorithms
\usepackage{subfig}       % for getting the subfigures e.g., "Figure 1a and 1b" etc.
\usepackage{url}          % for better support in handling and breaking URLs
\usepackage{comment}      % for commented text in .tex file

% add bibliographystyle required for example somestyle.bst
\bibliographystyle{somestyle}

\title

\begin{abstract}
Abstract goes here. No citations, table or figure references in abstract. 
\end{abstract}

\begin{document}

\maketitle

\section{......}
......
\subsection{......}

% add bibliography .bib file name without file extension .bib
\bibliography{mybib}

\end{document}
```

At times, what you see and what you get in LaTeX, defies the logic :)  
It can consume a lot of time, especially while switching between journal formats.  

If cited publications using \cite{someindex} are not appearing under References, or you are getting an [empty .bbl file](https://tex.stackexchange.com/questions/207664/bibtex-generates-an-empty-bbl-file), rename both .tex and .bib file to all small letters and same name with different extensions. Do not forget to update filename in .tex file using \bibliography{filename}. 
